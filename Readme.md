# Project: A static site generator in Go.
Usage of file handling, templating, and working with text.

## **1. Setup Project Structure**
Project folder:
```
/static-site-generator
  /templates
  /content
  /output
  main.go
```
- **`templates/`** will contain the HTML templates.
- **`content/`** will store the Markdown or content files (like blog posts).
- **`output/`** will be where the generated HTML files are saved.

## **2. Read Markdown Files**
Use the `blackfriday` library to parse Markdown files into HTML. Install it using:
```bash
go get github.com/russross/blackfriday/v2
```
`main.go` will need to read Markdown files, convert them to HTML, and then combine them with an HTML template.

## **3. Use Go’s `html/template`**
Create an HTML template in the `templates/` folder with placeholders to insert the content. For example:
```html
<!-- templates/default.html -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>{{.Title}}</title>
</head>
<body>
    <h1>{{.Title}}</h1>
    <div>{{.Content}}</div>
</body>
</html>
```

## **4. Process the Markdown Files**
Once I have the content files (Markdown), I’ll convert them into HTML and insert the HTML content into the template.

## **5. Generate the Static Site**
For each content file, the generator will:
1. Convert the Markdown to HTML.
2. Use the `html/template` package to apply the content to the template.
3. Write the result into the output directory.

## **6. Add More Features**
- **A command-line interface (CLI)**: Use flags or arguments to allow users to choose a template or specify content.
- **Customization options**: Add metadata like date, categories, and tags to the Markdown files.
- **CSS Templates**: Select a CSS Style from a selection
- **Responsive Design**: Make it all responsive..