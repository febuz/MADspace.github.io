---
layout: participant
title: Joost Hoeks
---
<p>My projects:</p>
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
    var out = '<table border="1"><tr><th>Url:</th><th>Updated at:</th><th>Stars:</th><th>Forks:</th></tr>';
    var i;
    for(i = 0; i < arr.length; i++) {
        out += '<tr><td><a href="' + arr[i].html_url + '" onclick="window.open(this.href); return false;">' + arr[i].name + '</a></td><td>' + arr[i].updated_at +'</td><td>' + arr[i].stargazers_count + '</td><td>' + arr[i].forks_count + '</td></tr>';
    }
    out += '</table>'
    document.getElementById('projects').innerHTML = out;
}
</script>

