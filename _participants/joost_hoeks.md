---
layout: participant
title: Joost Hoeks
---
<div id="projects"></div>

<script type="text/javascript">
var xmlhttp = new XMLHttpRequest();
var url = 'https://api.github.com/users/joosthoeks/repos?type=owner&sort=updated&direction=desc'

xmlhttp.onreadystatechange = function() {
    if (this.readyState == 4 && this.status == 200) {
        var myArr = JSON.parse(this.responseText);
        myFunction(myArr);
    }
};
xmlhttp.open('GET', url, true);
xmlhttp.send();

function myFunction(arr) {
    var out = '<div class="table-responsive">';
    out += '<table class="table table-striped table-bordered table-hover">';
    out += '<caption>My projects:</caption>';
    out += '<thead>';
    out += '<tr><th scope="col">#</th><th scope="col">Url:</th><th scope="col">Updated at:</th><th scope="col">Language:</th><th scope="col">Stars:</th><th scope="col">Forks:</th></tr>';
    out += '</thead>';
    out += '<tbody>';
    var i;
    for(i = 0; i < arr.length; i++) {
        out += '<tr><th scope="row">' + (i + 1) + '</th><td><a href="' + arr[i].html_url + '" onclick="window.open(this.href); return false;">' + arr[i].name + '</a></td><td>' + arr[i].updated_at +'</td><td>' + arr[i].language + '</td><td>' + arr[i].stargazers_count + '</td><td>' + arr[i].forks_count + '</td></tr>';
    }
    out += '</tbody>';
    out += '</table>';
    out += '</div>';
    document.getElementById('projects').innerHTML = out;
}
</script>

