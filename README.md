# Tech-Academy-Projects
While studying at The Tech Academy, I completed several assignments and worked on multiple projects in order to build my skill set and proficiency in HTML, CSS, JavaScript, Python, Django, SQL, C# and the .NET framework. I was taught how to think like a programmer in order to find creative solutions while writing clean and precise commented code. Completing these assignments and projects taught me several programming skills and gives me the confidence that I can learn any language or framework fairly quickly.

## C# / .NET Live Project
After completing The Tech Academy's C# and .NET course I was tasked with working with other developers to help develop a new Content Management System(CMS) for a local theatre company. This project was built utilizing ASP.NET MVC, Entity framework and C#. The goal was to create a simple web application that could be managed by those who are not necessarily tech savy. Our team used Microsoft Azure DevOps and practiced SCRUM processes including a daily meeting to discuss progress and roadblocks. This project had already started upon joining, this taught me the importance of quickly becoming famliar with a project and how to get up to speed quickly in order to make sizable contributions. 

### Home Page
I was first tasked with styling the home page of the theatre website. I utilized bootstrap as much as possible to create flexboxes which provided my basic page layout. I then added all the required content and images onto the page in the requested positions. I used CSS to style and position the content, images, links and buttons.

    /* ----- HOME PAGE STYLING ----- */
    .home-index--theatreLogo {
       padding-top: 100px;
       padding-bottom: 150px;
       text-align: center;
    }

    .home-index--theatreLogo img {
        width: 500px;
        height: 100px;
    }

    .home-index--container {
        float: left;
        padding: 10px;
    }

    .home-index--columnLeft {
        width: 64%;
        float: left;
    }

    .home-index--columnRight {
        width: 36%;
        float: right;
    }

    @font-face {
        font-family: Oswald;
        src: url('/webfonts/Oswald-VariableFont_wght.ttf') format('truetype');
    }

    .home-index--h2 {
        position: relative;
        font-family: Oswald;
        padding-bottom: 20px;
        padding-top: 60px;
    }

    .home-index--h2::after {
        position: absolute;
        bottom: 4px;
        content:'';
        display: block;
        border: 2px solid red;
        width: 80px;
    }

    .home-index--spotlight img {
        padding-top: 5px;
        width: 95%;
    }

    .home-index--sponsors img {
        padding-top: 15px;
        width: 32%;
    }

    .home-index--btn {
        background-color: #bd1a11;
        border-radius: 5px;
        border: none;
        color: #fffbfb;
        text-align: center;
        padding: 16px;
        text-decoration: none; 
        display: inline-block;
        font-size: 22px;
        width: 250px;
        height: 70px;
    }

    .home-index--donationsBtn {
        padding-top: 70px;
        padding-bottom: 10px;
    }

    .home-index--donationsBtn a:hover {
        color: white;
        opacity: 0.85;
        }

    .home-index--NAYA {
        padding-top: 845px;
    }

    .home-index--NAYA img {
        padding-left: 50px;
    }

### Creating the Blog Author Model
We utilized a code-first programming methodology for this project. As a result, I created a Blog Author model as well as a class defining it's properties. It was then necessary to apply migrations, update the database and add scaffolding to create the views.

    namespace TheatreCMS3.Areas.Blog.Models
    {
        public class BlogAuthor
        {
            [Key]
            public int BlogAuthorId { get; set; }
            public string Name { get; set; }
            public string Bio { get; set; }
            public DateTime Joined { get; set; }
            public DateTime? Left { get; set; }
        }
    }
    
### Blog Author Create / Edit pages 
I used Bootstrap and CSS for styling while utilizing Razor syntax to create and build out the create and edit pages for Blog Authors. I created text editors and text boxes while implementing placeholders and datepickers.

    <div class="BlogAuthor-CreateEdit--formContainer">
       <hr />
       @Html.ValidationSummary(true, "", new { @class = "text-danger" })

      <div class="BlogAuthor-CreateEdit--TextContainer">
        <div class="BlogAuthor-CreateEdit--Name">
          @Html.LabelFor(model => model.Name, htmlAttributes: new { @class = "control-label col-md-2" })
          <div class="col-md-10">
            @Html.EditorFor(model => model.Name, new { htmlAttributes = new { @class = "form-control" } })
            @Html.ValidationMessageFor(model => model.Name, "", new { @class = "text-danger" })
          </div>
        </div>

        <div class="BlogAuthor-CreateEdit--Bio">
          @Html.LabelFor(model => model.Bio, htmlAttributes: new { @class = "control-label col-md-2" })
          <div class="col-md-10">
            @Html.TextAreaFor(model => model.Bio, new { htmlAttributes = new { @class = "form-control" } })
            @Html.ValidationMessageFor(model => model.Bio, "", new { @class = "text-danger" })
          </div>
        </div>
      </div>
      
      <div class="BlogAuthor--DateTimeContainer">
        <div class="BlogAuthor-CreateEdit--DateTime">
          @Html.LabelFor(model => model.Joined, htmlAttributes: new { @class = "control-label col-md-2" })
          <div class="BlogAuthor-CreateEdit--datefield">
            @Html.EditorFor(model => model.Joined, new { htmlAttributes = new { @type="date", @class = "BlogAuthor-CreateEdit--datetime", placeholder = "mm/dd/yyyy" } })
            @Html.ValidationMessageFor(model => model.Joined, "", new { @class = "text-danger" })
          </div>
        </div>

        <div class="BlogAuthor-CreateEdit--DateTime">
          @Html.LabelFor(model => model.Left, htmlAttributes: new { @class = "control-label col-md-2" })
          <div class="BlogAuthor-CreateEdit--datefield">
            @Html.EditorFor(model => model.Left, new { htmlAttributes = new { @type="date", @class = "BlogAuthor-CreateEdit--datetime", placeholder = "mm/dd/yyyy" } })
            @Html.ValidationMessageFor(model => model.Left, "", new { @class = "text-danger" })
          </div>
        </div>
      </div>
        
      <div class="BlogAuthor-CreateEdit--BtnContainer">

        <div class="BlogAuthor-CreateEdit--backBtn">
          @Html.ActionLink("Back to List", "Index", null, new { @class = " btn btn-dark" })
        </div>

        <div class="BlogAuthor-CreateEdit--createBtn">
          <input type= "submit" value= "Create"  class=" btn btn-success " />
        </div>

      </div>
    </div>
    
 ### Blog Author Delete / Details page
I used Bootstrap and CSS for styling while utilizing Razor syntax to create and build out the delete and details pages for Blog Authors. I created Author cards utilizing Bootstrap that had toggling nav tabs at the top that linked to the authors social media accounts, bio and blog posts. 
 
    <!-- Toggling nav tabs -->

      <ul class="nav nav-tabs BlogAuthor-DetDel--NavContainer mt-5">
        <li class="active"><a data-toggle="tab" href="#details" class="btn btn-dark text-white BlogAuthor-DetDel--BtnTab">Author Details</a></li>
        <li><a data-toggle="tab" href="#blogposts" class="btn btn-dark text-white BlogAuthor-DetDel--BtnTab">Blog Posts</a></li>
      </ul>
      
      
     <!-- Tab content -->
     
    <div class="tab-content">
      <div id="details" class="tab-pane fade in active show">
        <div class="BlogAuthor-DetDel--header">

          <!--Author name -->
          <div class="BlogAuthor-DetDel--Name">
            <h3>@Html.DisplayFor(model => model.Name)</h3>
          </div>
          <!-- Social media accounts -->
          <div class="BlogAuthor-DetDel--socialMedia">
            <a href="https://www.facebook.com"><i class="fab fa-facebook fa-2x"></i></a>
            <a class="BlogAuthor-DetDel--insta" href="https://www.instagram.com"><i class="fab fa-instagram fa-2x"></i></a>
          </div>

        </div>
        <!-- Author Bio -->
        <p class="BlogAuthor-DetDel--Bio">@Html.DisplayFor(model => model.Bio)</p>
        <!--Author joined/left dates -->
        <div class="BlogAuthor-DetDel--datetimeContainer">
          <div class="BlogAuthor-DetDel--DisplayNameFor">
            <p><strong>@Html.DisplayNameFor(model => model.Joined)</strong></p>
            <p><strong>@Html.DisplayNameFor(model => model.Left)</strong></p>
          </div>
          <div class="BlogAuthor-DetDel--DisplayFor">
            <p>@Html.DisplayFor(model => model.Joined)</p>
            <p>@Html.DisplayFor(model => model.Left)</p>
          </div>
        </div>
      </div>
      <!-- Author's blog posts -->
      <div id="blogposts" class="tab-pane fade">
        <p>(Implemented in future stories).</p>
      </div>
    </div>
 
 
## Conclusion
The C# and .NET live project was incredibly fun, challenging, and immersive. This project gave me the chance to apply everything that I had learned in the course. It was a great and invaluable experience to work on a team and apply project methodologies. I enjoyed daily standup meetings, it was interesting to hear what others were working on. Listening to how they approached and solved the roadblocks they came across was very beneficial as it gave me ideas and insight on how to overcome my own future roadblocks. Working on a small piece of a larger project in the middle of its lifecycle taught me the importance of great teamwork and communication. It also taught me the importance of version control and I now feel comfortable and confident for when I am expected to utilize it responsibly working on my next team. Every aspect of this live project will be applied to my future technology career. I will use the methods and strategies I have been taught as well as the ones that I have learned were successful for other students to solve any and all future roadblocks. As challenging as the project was, I learned a lot and it built confidence for the future that I can do it.
