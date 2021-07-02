<h1>Horizon reports</h1>
<p class="lead">Welcome to a Jekyll project built on Bootstrap 5.0.2 to generate horizon reports using PDF Reactor.</p>
<h2>Step 1 - Setup repository</h2>
<p><strong>1.1. </strong>First of all you need to clone the repository:</p>
<p><code>git clone git@github.com:akolinski/horizon-reports.git</code></p>
<p><strong>1.2. </strong>Then navigate into the folder:</p>
<p><code>cd horizon-reports</code></p>
<h2>Step 2 - Serve and build the site</h2>
<p>You can rebuild the site by running <code>jekyll serve</code>, which launches a web server and auto-regenerates your site when a file is updated.</p>

<p><a href="http://127.0.0.1:4000/reports/example-report">http://127.0.0.1:4000/reports/example-report</a></p>

<p>When you are happy locally with your changes you can run a <code>jekyll build</code> to generate the necessary code for production. Then add, commit and push all your changes to the <code>gh-pages</code> branch. Which will deploy our site to GitHub pages. Viewable:

<p><a href="https://akolinski.github.io/reports/example-report">https://akolinski.github.io/reports/example-report</a></p>

<h2>Step 3 - Style with SASS</h2>
<p class="lead">Jekyll compiles sass out of the box.</p>
<p><strong>3.1. </strong>All the project's dependencies are package managed in the <code>_sass</code> folder. Go into the<code>_sass</code> folder and run a <code>yarn install</code>.</p>
<p><strong>3.2. </strong>Add any custom styles to the _base.scss file. If you are already running a <code>jekyll serve</code> jekyll will identify your changes and compile. Any errors will be presented in terminal.</p>

<h2>Step 4 - Creating reports</h2>
<p>Reports live in the _posts directory. You’ll find an example report in the <code>_posts</code> directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site by running <code>jekyll serve</code>, which launches a web server and auto-regenerates your site when a file is updated.</p>

<p><a href="http://127.0.0.1:4000/reports/example-report">http://127.0.0.1:4000/reports/example-report</a></p>
<p><a href="https://akolinski.github.io/reports/example-report">https://akolinski.github.io/reports/example-report</a></p>

<p>To add new reports, simply add a file in the <code>_posts</code> directory that follows the convention <code>YYYY-MM-DD-name-of-report.html</code> and includes the necessary front matter. Take a look at the source for one of the example reports to get an idea about how it works.</p>

<h2>Step 5 - Setup Postman</h2>
<p><strong>5.1. </strong>Download Postman first: <a href="https://www.postman.com/downloads" target="_blank">https://www.postman.com/downloads</a></p>
<p><strong>5.2. </strong>Then open up Postman and click on <code>new</code> to create a new request</p>
<p><strong>5.3. </strong>Enter <code>https://cloud.pdfreactor.com/service/rest/convert.pdf</code> as the request URL and make sure you are sending a POST request</p>
<p><strong>5.4. </strong>Click on <code>body</code> > <code>raw</code> and paste this code:</p>

<p><code class="d-block">
    {<br>
    &nbsp;&nbsp;"document": "https://akolinski.github.io/horizon-reports/reports/example-report",<br>
    &nbsp;&nbsp;"conformance": "PDFUA1",<br>
    &nbsp;&nbsp;"addLinks": 1,<br>
    &nbsp;&nbsp;"addBookmarks": 1,<br>
    &nbsp;&nbsp;"javaScriptMode": "ENABLED_TIME_LAPSE",<br>
    &nbsp;&nbsp;"viewercodeferences": [<br>
    &nbsp;&nbsp;&nbsp;&nbsp;"FIT_WINDOW",<br>
    &nbsp;&nbsp;&nbsp;&nbsp;"PAGE_MODE_USE_THUMBS"<br>
    &nbsp;&nbsp;]<br>
    }
</code></p>
<p><small>* Note if you paste in Postman and get a error please validate the above here: https://jsonlint.com</small></p>

<p><strong>5.5. </strong>Click on <code>Send</code></p>
<p><strong>5.6. </strong>Click on <code>Save Response</code> and then <code>Save to a file</code></p>

<div class="alert alert-success p-1"><p class="m-0"><strong>Wooohooo!</strong> Your PDF has been created. Open the PDF up on your computer and see what it looks like.</p></div>

<h4>References</h4>
<ul>
    <li><a target="_blank" href="https://www.pdfreactor.com/product/doc_html/index.html#DefaultStyleRules">https://www.pdfreactor.com/product/doc_html/index.html#DefaultStyleRules</a></li>
    <li><a target="_blank" href="https://shopify.github.io/liquid/">https://shopify.github.io/liquid</a></li>
    <li><a target="_blank" href="https://www.taniarascia.com/make-a-static-website-with-jekyll/">https://www.taniarascia.com/make-a-static-website-with-jekyll</a></li>
    <li><a target="_blank" href="https://forestry.io/blog/how-i-reduced-my-jekyll-build-time-by-61/">https://forestry.io/blog/how-i-reduced-my-jekyll-build-time-by-61</a></li>
    <li><a target="_blank" href="https://michaelsoolee.com/undo-gem-based-jekyll-theme/">https://michaelsoolee.com/undo-gem-based-jekyll-theme</a></li>
    <li><a target="_blank" href="https://talk.jekyllrb.com/t/scss-specific-background-image-link/766">https://talk.jekyllrb.com/t/scss-specific-background-image-link/766</a></li>
    <li><a target="_blank" href="https://guide.pressbooks.com/chapter/changing-page-margins-in-pdf-exports/">https://guide.pressbooks.com/chapter/changing-page-margins-in-pdf-exports/</a></li>
    <li><a target="_blank" href="https://www.makeuseof.com/format-web-page-for-printer/#handling-page-breaks">https://www.makeuseof.com/format-web-page-for-printer/#handling-page-breaks</a></li>
</ul>

<h4>FAQs</h4>
<h5>How to reference images in scss with jekyll</h5>
<code>background-image: url("#{$baseurl}/assets/images/filename.svg");</code>
