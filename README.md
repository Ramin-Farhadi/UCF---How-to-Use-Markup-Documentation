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
<div style=”mt-3”> </div>
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

<li>We never use nested sections in UCF</li>

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

- Separate it into three paragraphs

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
