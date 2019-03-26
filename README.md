https://youtu.be/B4xexNiD6jE

# Api-app-for-BBC-Headline
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>BBC latest -news</title>

    <!-- Bootstrap core CSS -->
    <link href="https://bootswatch.com/simplex/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" href="css/style.css">
  </head>

  <body>

    <nav class="navbar navbar-inverse">
      <div class="container">
        <div class="navbar-header">
          <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#navbar" aria-expanded="false" aria-controls="navbar">
            <span class="sr-only">Toggle navigation</span>
            <span class="icon-bar">BBC</span>
            <span class="icon-bar">News</span>
            <span class="icon-bar">App</span>
          </button>
          <a class="navbar-brand" href="#">BBC news app finder app by Jahurul</a>
        </div>
        <div id="navbar" class="collapse navbar-collapse">
          <ul class="nav navbar-nav">

          </ul>
        </div><!--/.nav-collapse -->
      </div>
    </nav>

    <div class="container">
            <div id="profile1"></div>
      
   

    </div><!-- /.container -->

    <script src="https://code.jquery.com/jquery-3.1.1.js" integrity="sha256-16cdPddA6VdVInumRGo6IbivbERE8p7CQR3HzTBuELA="
  crossorigin="anonymous"></script>
  
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
   <!-- <script src="js/main.js"></script>-->
   <script>
$(document).ready(function(){
   // $("#Search").keyup(function(e){
//var num=e.target.value;
//console.log(num);
$.ajax({
     url:'https://newsapi.org/v1/articles?source=bbc-news&sortBy=top&apiKey=92638b5c190a49319ed6e391cff00cfb',
    }).done(function(data){
       console.log(data);
    for(var i=0;i<data.articles.length;i++){
       $('#profile1').append(`
          <p> <img src="${data.articles[i].urlToImage}"></p>
           <br/>
           <a href="http://www.bbc.com/news/world" <h3 class="panel-title">Title:${data.articles[i].title}</h3></a>
            
            <br/>
            <h3 class="panel-title">Author:${data.articles[i].author}</h3>
             
            <h3 class="panel-title">Description:${data.articles[i].description}</h3>
             <br/>
           `);
       }
      });    
     
    });
     </script>
  </body>
</html>
