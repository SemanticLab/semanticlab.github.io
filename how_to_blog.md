

How to add a new blog post. If you don't want to run Jekyll to develop the blog post locally. 

* Prepare your blog text and media assets
* Download the blog template: https://github.com/SemanticLab/semanticlab.github.io/blob/master/blog/_posts/2025-01-01-TEMPLATE.html
* Rename it using to the date you want the blog publushed plus a keyword/phrase to help identifiy it
* Rename your media assests to something like `"blog_<phrase>_1.png"` so like "blog_TEMPLATE_1.png" "blog_TEMPLATE_2.png" etc.
* Upload them here: https://github.com/SemanticLab/semanticlab.github.io/tree/master/assets
* Edit the HTML file locally on your computer in a text editor.
* Change the header metadata at the top of the page (if you set the date to a date in the future it will not showup on the site until that date). If you dont want to include something like subtile make it empty qoutes: ""
* The "permalink" value is where the blog URL will show up
* You can use any HTML you want in the blog doc, you probably want to go pharagraph by pharagraph using this format:

```
  <div class="content">

    <p>
      Phara 1
    </p>
    <p>
      Phara 2
    </p>    
    <p>
      etc...
    </p>


  </div>
```
You can look at https://github.com/SemanticLab/semanticlab.github.io/blob/master/blog/_posts/2025-02-28-COMMUNICATING.html it is pretty simple

* Don't forget to make things linkable using `<a href=""></a>` tags
* To link to images you uploaded ues "/assets/blog_whatever_1.png" for examplke `<img src="/assets/blog_whatever_1.png" alt="ALT TEXT HERE"/>`
* Once you finish editing upload the doc back to https://github.com/SemanticLab/semanticlab.github.io/blob/master/blog/_posts/
* The page will redbuild but it will take a min, you can check https://github.com/SemanticLab/semanticlab.github.io/actions to see its status
* Once the file is up and you want to make little changes you can use the github editor built into the site.
