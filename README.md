# Tech-Academy-Projects
While studying at The Tech Academy, I completed several assignments and worked on multiple projects in order to build my skill set and proficiency in HTML, CSS, JavaScript, Python, Django, SQL, C# and the .NET framework. I was taught how to think like a programmer in order to find creative solutions while writing clean and precise commented code. Completing these assignments and projects taught me several programming skills and gives me the confidence that I can learn any language or framework fairly quickly.

## C# / .NET Live Project
After completing The Tech Academy's C# and .NET course I was tasked with working with other developers to help develop a new Content Management System(CMS) for a local theatre company. This project was built utilizing ASP.NET MVC, Entity framework and C#. The goal was to create a simple web application that could be managed by those who are not necessarily tech savy. Our team used Microsoft Azure DevOps and practiced SCRUM processes including a daily meeting to discuss progress and roadblocks. This project had already started upon joining, this taught me the importance of quickly becoming famliar with a project and how to get up to speed quickly in order to make sizable contributions. 

### Home Page
I was first tasked with styling the home page of the theatre website. I utilized bootstrap as much as possible to create flexboxes which provided my basic page layout. I then added all the required content and images onto the page in the requested positions. I used CSS to style and size the content, images, links and buttons.

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
