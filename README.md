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
Bootstrap. The diTerence is that we prefer to use it in a shortcode style. However, the
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

+ We use the built-in classes
[container]
    [row class=”mt-5”]
        [col xs=”6”][/col]
        [col xs=”6”][/col]
    [/row]
[/container]
```
