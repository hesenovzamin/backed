 public class newsController : Controller
    {
        private back_endEntities db = new back_endEntities();
        
        public ActionResult Index()
        {
            var news = db.news.Include(n => n.Category);
            return View(news.ToList());
        }
        
        
        
        
        
        @model IEnumerable<WebApplication11.Models.news>



@foreach (var item in Model) {

  <div class="container">
      <div class="cihisse">
          <div class="Heading">@item.Heading</div>

          <div class="Date">@item.date</div>

          <div class="text">@item.news1</div>

          <div class="Category">@item.Category.Category1</div>
      </div>
  </div>

        public ActionResult Create()
        {
            ViewBag.Cat_id = new SelectList(db.Categories, "id", "Category1");
            return View();
        }
