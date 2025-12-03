<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<title>قصص للأطفال</title>

<style>
    body {
        font-family: "Cairo", Arial, sans-serif;
        background: #ffffff;
        text-align: center;
        padding: 20px;
    }

    h1 {
        color: #000;
        font-size: 42px;
        margin-bottom: 5px;
    }

    p {
        color: #000;
        font-size: 20px;
        margin-top: 0;
        font-weight: bold;
    }

    .icon {
        width: 120px;
        margin: 15px auto;
        display: block;
    }

    button {
        padding: 15px 25px;
        font-size: 20px;
        border: none;
        border-radius: 15px;
        margin: 10px;
        cursor: pointer;
        transition: 0.3s;
        color: #fff;
        font-weight: bold;
        box-shadow: 0 4px 10px #0003;
    }

    button:hover { transform: scale(1.12); }

    #btn1 { background: #ff5f5f; }
    #btn2 { background: #55d97b; }
    #btn3 { background: #f1c40f; }

    #storyBox {
        background: #fff;
        width: 90%;
        max-width: 750px;
        margin: 25px auto;
        padding: 25px;
        border-radius: 20px;
        box-shadow: 0px 0px 15px #0003;
        font-size: 22px;
        display: none;
        text-align: left;
        border: 3px dashed #66a6ff;
        line-height: 1.7;
    }

    .storybook-title {
        font-size: 28px;
        font-weight: bold;
        color: #66a6ff;
        margin-bottom: 10px;
        text-align: center;
    }
</style>

</head>
<body>

<h1>قصص للأطفال</h1>
<p>مقدم من الطالب عادل عفت إلى مدرسة سفاجا الرسمية للغات</p>

<img class="icon" src="https://cdn-icons-png.flaticon.com/512/2037/2037719.png">

<button id="btn1" onclick="tellStory(1)">Sam Story</button>
<button id="btn2" onclick="tellStory(2)">Mr. Kareem Story</button>
<button id="btn3" onclick="tellStory(3)">Omar Story</button>

<div id="storyBox">
    <div class="storybook-title" id="storyTitle"></div>
    <div id="storyText"></div>
</div>

<script>
function speak(text) {
    let voice = new SpeechSynthesisUtterance(text);
    voice.lang = "en-US";
    voice.rate = 1;
    voice.pitch = 1.4;
    speechSynthesis.cancel();
    speechSynthesis.speak(voice);
}

function tellStory(num) {

    let titles = {
        1: "Sam's Story",
        2: "Mr. Kareem's Story",
        3: "Omar's Story"
    };

    let story1 = `
Hi! My name is Adam, and I want to tell you a story about tolerance.
A new boy joined our school. His name was Sam, and he didn’t speak English very well.
Some kids made fun of the way he talked. I felt bad, so I went to him and said,
“Don’t worry Sam, you can play with us.”
His face lit up with a big smile. That day, we all learned that accepting others 
makes school a happier place.
`;

    let story2 = `
Hello again, it’s Adam! Today’s story is about my neighbor Mr. Kareem.
He had two cats that always fought. One day, he put food in one bowl so they had to share.
Something surprising happened! The cats stopped fighting and began eating peacefully.
Mr. Kareem told me, “Adam, if animals can learn tolerance, humans should too.”
I remembered that lesson forever.
`;

    let story3 = `
Hey, it’s Adam again with my last story.
In my football team, there was a boy named Omar. He wasn’t good at kicking,
so some kids didn’t want him on the team. I told them,
“Everyone deserves a chance.”
We helped Omar practice every day. And guess what?
He scored the winning goal in the final match!
We all shouted and celebrated. That day we learned that tolerance and support
can help anyone become amazing.
`;

    document.getElementById("storyBox").style.display = "block";
    document.getElementById("storyTitle").innerText = titles[num];

    if (num === 1) {
        document.getElementById("storyText").innerText = story1;
        speak(story1);
    }
    if (num === 2) {
        document.getElementById("storyText").innerText = story2;
        speak(story2);
    }
    if (num === 3) {
        document.getElementById("storyText").innerText = story3;
        speak(story3);
    }
}
</script>

</body>
</html>
