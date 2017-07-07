---
layout: base
title: Photography
description: Photography
cover-text: Portraits
cover-image: /images/portraits/people/r-large.jpg
nav: true
nav-order: 3
---


<div class="coverphoto" style="background-image:url({{page.cover-image}})"><h1 class="covertext">{{ page.cover-text}}</h1></div>
<div class="page-content container">
 <p class="text-center">More on <a href="https://www.flickr.com/photos/{{ site.flickr_username }}/" target="_blank">Flickr
            <i class="fa fa-lg fa-flickr" aria-hidden="true"></i>
        </a></p>
        <br>
        <div id ="loading"><h2 class="text-center">Loading...</h2></div>
<div class="grid">

           <div class="grid-sizer"></div>
          {% for photo in site.data.photography1 %}
            <div class="grid-item"><a class="grid-item-link"><div class="overlay-cover"></div><img class="img-responsive" src="{{ photo.src }}"></a></div>
{% endfor %}
 {% for photo in site.data.photography2 %}
            <div class="grid-item"><a class="grid-item-link"><div class="overlay-cover"></div><img class="img-responsive" src="{{ photo.src }}"></a></div>
{% endfor %}
</div>
</div>


<!-- <div class="coverphoto" style="background-image:url({{page.cover-image}})"><h1 class="covertext">{{ page.cover-text}}</h1></div> -->
<div class="page-content container">
<div class="grid">

           <div class="grid-sizer"></div>
         
</div>
</div>

<style>
    
    .covertext {
         position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: white;
  text-align: center;
    }
    
    .coverphoto {
    height: 220px;
    width: 100%;
  
    background-size: 100%;
    /*background-attachment: scroll;*/
    background-position: 50% 45%;
    position: relative;
}
    
    .grid-item { width: 100%; }



@media only screen 
and (min-width : 450px) {
 .grid-item { width: 50%; }
}
@media only screen 
and (min-width : 768px) {
 .grid-item { width: 33.3333%; }
}


/* Desktops and laptops ----------- */
@media only screen 
and (min-width : 1224px) {
 .grid-item { width: 25%; }
}

/* Large screens ----------- */
@media only screen 
and (min-width : 1824px) {
 .grid-item { width: 20%; }
}
  
    
    .grid-item .grid-item-link {
    display: block;
    overflow: hidden;
    position: relative;
    text-decoration: none;
    overflow: hidden;
}

    
.grid-item { 
    visibility: hidden;
    padding: 0 3px 3px 0;
    }
    
   /* .grid-item:hover .overlay-cover {
    opacity: 0.5;
    background-color: #000000;
}

    .grid-item .overlay-cover {
    position: absolute;
    width: 101%;
    height: 101%;
    z-index: 7;
    transition: all 200ms ease-in-out;
}*/
  .grid{
         margin: auto;
         width: 100%;
    }
    
  

    
</style>
<div style="height:100px;"></div>
<script>
    
//  $(window).load(function() {
// function masonryGridInit(){
        
//         // Grid Container
//         var gridContainer = $('.grid');

//         // Grid Options
//         var gridOptions = {
//             itemSelector: '.grid-item',
//             percentPosition: true,
//             transitionDuration: '0'
//         };

//         // layout Masonry after each image loads
//         gridContainer.imagesLoaded(function() {
//             gridContainer.masonry(gridOptions);
            
//             // Bind Event Listener To Layout
//             gridContainer.masonry('on', 'layoutComplete', function () {
//                 console.log('layout done');
//                 // Init Scroll Reveal
//                  if (typeof sr == 'undefined') {
//                     window.sr = new ScrollReveal({ duration: 800, distance: '80px' });
//                 }
//                 sr.reveal('.grid-item',20);
              
//             });
//         });
// }
//     // Init Masonry Layout 
//     $(window).on('load scroll', function(e){
//         masonryGridInit();
//     });

//  });

 
//    
$(window).load(function() {
//// init Masonry
var $grid = $('.grid').masonry({
 // options...
    itemSelector: '.grid-item',
   percentPosition: true,
   transitionDuration: 0
});
// layout Masonry after each image loads
$grid.imagesLoaded(function(){
 
  $('#loading').hide();
  /* other stuff... */
}).progress( function() {
 $grid.masonry('layout');
});
   
   
   function onLayout() {
 console.log('layout done');
}

$grid.one( 'layoutComplete', function() {
 console.log('layout done, just this one time');
    if (typeof sr == 'undefined') {
                   window.sr = ScrollReveal();
               }
              sr.reveal('.grid-item');
});
//    
//    // JavaScript
//window.sr = ScrollReveal();
//sr.reveal('.grid-item');
    });
</script>

