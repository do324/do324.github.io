---





layout: post





title:  "instaclone_project"





date:   2019-03-23 21:03:36 +0530





categories: Javascript Python AJAX Django





---





I made a insta clone. it is writeen by python, js, html

I made #, posing, login, sign in functions like instagram.


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

```python
{% extends "post/layout.html" %}
{% load static %}


{% block head %}
    <link rel="stylesheet" href="{% static 'css/new_post.css' %}">
{% endblock %}



{% block content %}
    <div id="main_container">

        <div class="post_form_container">
            <form action="#" class="post_form" method="post" enctype="multipart/form-data">
                <div class="title">
                    New Post
                </div>
                <div class="preview">
                    <label for="id_photo">
                        <div class="upload">
                            <div class="post_btn">
                                <div class="plus_icon">
                                    <span></span>
                                    <span></span>
                                </div>
                                <p>포스트 이미지 추가</p>
                                <canvas id="imageCanvas"></canvas>
                            </div>
                        </div>
                    </label>
                </div>

                {% csrf_token %}
                {{ form.as_p }}

                <input type="submit" class="submit_btn" value="저장">
            </form>
        </div>
    </div>

<script>
var fileInput = document.querySelector("#id_photo")
fileInput.addEventListener('change', handleImage);
var canvas = document.getElementById('imageCanvas')
var ctx = canvas.getContext('2d');

    
function handleImage(e){
    var reader = new FileReader();
    reader.onload = function(event){
        var img = new Image();
        img.onload = function(){
            canvas.width = 300;
            canvas.height = 300;
            ctx.drawImage(img,0,0,300,300);
        };
        img.src = event.target.result;
    };
    reader.readAsDataURL(e.target.files[0]);
}

</script>

{% endblock %}
```
















