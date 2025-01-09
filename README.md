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

<code style="color : Red"> Instead of this </code> <s>`<div style=”margin-top:30px”> </div>`</s>
<code style="color : Green"> We use the built-in classes </code> `<div style=”mt-3”> </div>`
