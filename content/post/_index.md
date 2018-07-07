+++
[menu]
     [menu.main]
        name = "Blog"
        weight = 4
        identifier = "blog"
date = "2017-01-24T16:33:27+03:00"
title = "posts"
sharingicons = false
menu = "navbar"
+++

<html>
where is this text?
<style>
.parallax {
    /* The image used */
    background-image: url("img/blog.jpg");
    /* Set a specific height */
    height: 400px;
    /* Create the parallax scrolling effect */
    background-attachment: fixed;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
}
</style>
<div class="parallax"></div> 
        {{ $paginator := .Paginate (where .Data.Pages "Type" "post") }}
        {{ range $paginator.Pages }}
        {{ .Render "summary" }}
        {{ end }}
        {{ partial "bloc/content/pagination.html" . }}
</html>

