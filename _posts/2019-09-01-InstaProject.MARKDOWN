---





layout: post





title:  "instaclone project"





date:   2019-03-23 21:03:36 +0530





categories: Javascript Python AJAX Django





---





I made a insta clone. it is writeen by python, js, html

I made #, posing, login, sign in functions like instagram.

check out instaclone page here [My instaclone](https://instaclone-tfzvo.run.goorm.io/post)


Check out [My github](https://github.com/do324/instaclone) for see more code.









```javascript
const tapContainer = document.querySelector('.about');
const flex_Container = document.querySelectorAll('.contents_container');
const taps = document.querySelectorAll('.about > span');


function openCity(e){
    let elem = e.target;
    
    for (var i = 0; i < flex_Container.length; i++) {
        flex_Container[i].classList.remove('active');
        taps[i].classList.remove('on');
    }
    
    if(elem.matches('[class="nick_name"]')){
        
        flex_Container[0].classList.add('active');
        taps[0].classList.add('on');
        
    }else if(elem.matches('[class="book_mark"]')){
        
        flex_Container[1].classList.add('active');
        taps[1].classList.add('on');
        
    }
    
}


tapContainer.addEventListener('click', openCity);
```


















