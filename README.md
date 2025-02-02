# UCF Markup and Style Best Practices

## (How to Use HTML and CSS)

Since UCF uses its own built-in themes and plugins, we are using customized markup and
styles. Historically, we have been using the Athena framework, which is a customized
version of Bootstrap 4. As a result, we don’t have some of the classes found in newer
versions, such as .overflow and other newer classes.

Since we use the Athena framework, we have a specific way of writing code, which we will
discuss in the following bullet points.

<ul>
<li> We avoid using custom CSS or inline CSS and aim to stick to Athena framework
classes or Bootstrap classes. For example:
</li>

```diff
- Instead of this
<div style=”margin-top:30px”> </div>

+ We use the built-in classes
<div class=”mt-3”> </div>
```

<li>
When writing HTML code, we prefer to use the grid system, which works exactly like
Bootstrap. The diference is that we prefer to use it in a shortcode style. However, the
traditional Bootstrap method also works well, and for nested elements, we may opt
for the traditional Bootstrap version to avoid code conflicts.
</li>

```diff
- Instead of this
<div class=”container”>
    <div class=”row mt-5”>
        <div class=”col-6”></div>
        <div class=”col-6”></div>
    </div>
</div>

+ We prefer to use short code version:
[container]
    [row class=”mt-5”]
        [col xs=”6”][/col]
        [col xs=”6”][/col]
    [/row]
[/container]
```

```diff
- Nested blocks won't be rendered correctly so Instead of this
[container]
    [row class=”mt-5”]
        [col xs=”6”]
            [container]
                [row]
                    [col][/col]
                    [col][/col]
                [/row]
            [/container]
        [/col]
        [col xs=”6”][/col]
    [/row]
[/container]

+ In this case we prefer to use the old school bootstrap methed.
<div class="container">
    <div class="row">
        <div class="col-6">
            <div class="container">
                <div class="row">
                    <div class="col-12"></div>
                    <div class="col-12"></div>
                </div>
            </div>
        </div>
        <div class="col-6"></div>
    </div>
</div>
```

<li>We always try to avoid using unnecessary div tags. When we have only one [row], we try not to use it at all.</li>

```diff
- Instead of this
[container]
    [row]
        "This is my content"
    [/row]
[/container]

+ Use this
[container]
    "This is my content"
[/container]
```

<li>While we are allowed to use nested sections in general, because of the structure and architecture of markup, we never use nested sections in UCF</li>

```diff
- Instead of this
<section id="section-1">
    <section id="section-2"></section>
</section>

+ Use this
<section id="section-1"></section>
<section id="section-2"></section>
```

<li>Each paragraph should be separated</li>

```diff
- Instead of this
<p>
What is Lorem Ipsum?
Lorem Ipsum is simply dummy text of the printing and typesetting industry.

Why do we use it?
It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English.

Where does it come from?
Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old.

</p>

+ Separate it into three paragraphs

<p>
What is Lorem Ipsum?
Lorem Ipsum is simply dummy text of the printing and typesetting industry.
</p>
<p>
Why do we use it?
It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English.
</p>
<p>
Where does it come from?
Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old.
</p>
```

<li>When we upload a new image (img tag), we must ensure to update the wp-image-**** class. This class is related to the lazy loading of the page. Additionally, to meet W3C compliance, we must add the alt attribute every time we use an image. </li>

```diff

+ Add the class
<img src="https://..." alt="Privacy Cluster" class="size-full wp-image-76477 img-fluid" />

```

<li>For better accessiblity, we should always try to add type when we use button tag.</li>

```diff

+ Always add type to buttons if don't, it will act like a submit button by default.
<button type="button" class="btn btn-primary mt-3" onclick="iconSelector(event)" data-bs-toggle="modal" data-bs-target="#iconModal">Cick to Select</button>

```

<li>When we want to add space between two elements in HTML, we prefer using margin instead of padding. This ensures that spacing is applied externally, maintaining the correct box model structure.</li>

```diff
- Instead of this
<div class="col pb-3">

+ We use this
<div class="col mb-3">

```

<li > Using an image in an <h*> tags (h1, h2, h3 ... ) is generally discouraged for SEO due to its potential drawbacks. </li>

```diff
- Instead of using img tags inside the h1

<h1><img src="test.jpg" alt="something" /></h1>

+ It can be used like
<div>
<h1>Here is my title</h1>
<img src="test.jpg" alt="something"/>
</div>

```

<li> Make sure to re-upload images when migrating the code from the test environment to production.</li>

<p> When migrating content from the test environment to production, ensure that all links and images are updated. In the test environment, links start with `wwwtest`, whereas in production, they start with `www`.</p>

```diff
- Do not use `wwwtest` links in production.
<img src="wwwtest.my-image.jpg" />
or
<a href="wwwtest.ucf.edu/destination" > My link </a>

+ Instead, use the correct production links. Note: Images must be re-uploaded in production.
<img src="www.my-image.jpg" />
or
<a href="www.ucf.edu/destination" > My link </a>
```
