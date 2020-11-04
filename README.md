# landing page 
In this page we 've built a navigation bar (menu) that contains four iteams related by 4 sections and when
we click on any iteam of the navbar it must scrolling to it's section dynamically.

languages 
======
i've used four languages to build this page and they 're :
1. HTML (used to  describes the structure of a Web page) 
2. CSS  (used to design the content of the page)
3. JavaScript (used to program the behavior of web pages)
4. JQuery (used to simplifies JavaScript .) <br/>

now i'll talk briefly aboat them 

HTML
======
First i built HTML file then connect it to another 2 files (CSS,JavaScript)<br/>
second created ul (unorder list) to build the navbar and used li (list iteam) to build it's iteams . <br/>
third created four divs to build four sections and added to each one of them id ( BEEF-STICKS , CHICKEN-DRUMSTICKS , BURGAR-SANDWISH , VEGETABLE-RICE) so they can help in scroll process

CSS
======
i used it to design the content of the page by giving some properties for the selectors and classes <br/>
for example :
1. adding class (navbar) to (ul) so i can design navigation menu 
2. adding class (block) to sections so i can design the sections 
3. using selector (li) so i can design the iteams 

JavaScript & jQuery
====== 
I used them to program the behavior of the web page and the navigatio menu  <br/>
now let's see what every section do in the JavaScript file : <br/>

1. 
$(document).ready( function() {
let all_li = document.querySelectorAll('li');
all_li.forEach( (li) => {document.createElement('a');  
})
<br/>- (In this section the links (anchors) 're created dynamically and give each (li) one (a) by using forEach() Loop )
2. 
$('.navbar li ').click(function(e){
      e.preventDefault();
      $('html, body').animate({
        scrollTop : $('#' + $(this).data('scroll')).offset().top + 1
      },1500)
    });
<br/>- (In this section the elements are scrolling smoothly  )   
3.
$('.navbar li  ').click(function(){
       $(this).addClass('active').siblings().removeClass('active');
   }) 
<br/>- (this section built to highlight each iteam that was scrolled to it's secton by adding Active Class on navbar link and remove the siblings)    
4.

   $(window).scroll(function(){
    $('.block').each(function(){
      if($(window).scrollTop() > $(this).offset().top){
        console.log($(this).attr('id'));
        var blockId = $(this).attr('id');
        $('.navbar  a').removeClass('active ');
        $('.navbar li a[data-scroll="'+blockId+'"]').addClass('active ');
      }})
   })
<br/>- (sync navbar links with sections  )      
   
