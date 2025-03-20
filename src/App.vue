<template>
  <header>
    <h1>高程小作文生成器</h1>
    <div class="about">
      <a href="https://github.com/Linho1219/TJGCexcuse">Github</a>
    </div>
    <div class="panel">
      <select v-model="excType">
        <option value="copy">抄袭</option>
        <option value="beingcopied">被抄袭</option>
        <option value="format">格式</option>
        <option value="encoding">编码</option>
      </select>
      <input type="text" placeholder="信息" v-model.trim="personInfo" />
      <input
        type="text"
        placeholder="另一个人信息"
        v-model.trim="personInfo2"
        v-if="excType === 'copy' || excType === 'beingcopied'"
      />
    </div>
  </header>
  <main>
    <p v-if="excType==='copy'">
      沈坚老师您好，我是{{ personInfo }}，真的非常对不起，这次的高程作业我抄袭了{{ personInfo2 }}的作业，因为时间紧急，自己又对代码并不敏感，我上课不专心听讲，也没有关注群里的消息，所以我甚至不知道有程序编写的作业要完成，快到截止日期的时候，看见没写的作业，我感到十分慌张，所以去求我认识的人把作业给我抄。本来他们没人会给我看的，但是我不断摇晃别人的胳膊，一直在别人身边说话，才使得寝室里的{{ personInfo2 }}把他的作业给了我。我深知写作业的目的是为了理解和运用，也并没有直接照搬，在他的帮助下独立写了自己的版本，这个同学也有看到过。但在提交时，可能是因为命名时的疏忽，我的部分题目直接提交了他的文件，对他造成了不可挽回的影响。我知道抄袭和被抄袭的后果都十分严重，但是我因为懒散，明知故犯。发这段话之前也看到了您群里发的内容，我不能承担他发出代码的后果，我也只能恳求您再给我和他一次机会。他的本意并不是让我照搬他的作业，我也并非想要这么做。我对于自己不认真学习，临时进行抄袭的行为感到非常后悔，都是因为我学习态度不端正，做事不认真才会出现这种情况。我心甘情愿接受老师的一切惩罚，并且保证自己以后独立完成学校的各项作业。{{ personInfo2 }}并没有自愿给出作业，而是在我的软磨硬泡之下才无可奈何地把作业给我抄。恳求老师能对{{ personInfo2 }}手下留情，我对抄袭作业这件事负全部责任，我自愿把对{{ personInfo2 }}的一切惩罚转移到我头上。都是因为我的错才让{{ personInfo2 }}蒙受冤曲。我今后一定改过自新，重新审视自己对待学习的态度，为高程付出更多精力，并保证日后的作业完全独立完成，上课一定专心听讲。绝对不会再抄任何人的作业。真的非常非常对不起。再次向您道歉。
    </p>
    <p v-if="excType==='beingcopied'">
      沈坚老师您好，我是{{ personInfo }}，之前{{ personInfo2 }}向我请教代码怎么写，因为他总是报错，想和我的代码对照看一下问题出在哪，因为当时我和他不在一起，我来不及回宿舍当面和他说，又一直软磨硬泡，所以为了方便直接把这道题的代码发给他让他自己研究一下，因为{{ personInfo2 }}自己也写了代码，所以我发给他代码目的是为了核对而非给他抄袭。会发生这样的事我深感抱歉，这是由于我没有采用正确的方式帮助同学，没有遵守规则纪律，才产生了这样严重的后果，对此我有不可推卸的责任，我已经深刻认识到了自己的错误，我也愿意自己的愚蠢承担责任。抄作业是对别人的劳动成果的不尊重，而把作业直接发出去是对我自己的劳动成果的不尊重，缺乏安全意识，缺乏规则意识，存在侥幸心理，因此我心甘情愿担负责任。但是，我还是想恳求老师能够给我们继续学习高程的机会，希望老师看在我们的行为动力是为了学习知识、找到自己错误；而非不劳而获、有意抄袭，能够手下留情，再给我们最后机会，我们保证以后会采用正确的学习方法，绝不会再有类似的情况发生，如若再犯，我们甘愿重修，绝无二话。一切规则说到底是为了让同学学到知识，因此我们保证绝对不会再有自作聪明的行为发生，端正学习态度，认真学习。我们明白我们的命运已不在自己手中，所以希望老师能够高抬贵手，感激不尽。
    </p>
    <p v-if="excType === 'format'">
      沈坚老师您好，我是{{ personInfo }}，非常抱歉，这次的高程作业我犯了一个非常低级的错误，就是没有认真阅读所给的材料和要求，没有按照规定的格式提交代码。我对于作业的格式要求完全没有注意到，导致我提交的作业格式完全错误。这是我粗心大意的表现，没有对作业要求进行仔细研究和理解。我深感愧疚和后悔，因为这个错误是完全可以避免的。我明白作业的格式要求是为了让我们更好地理解和运用所学的知识，而我却因为自己的疏忽而犯下了这个错误。我对自己的粗心行为深感羞愧，我愿意承担由此带来的一切后果。我保证以后会更加细心和认真对待作业的要求，确保不再犯类似的错误。再次向您道歉，希望能得到您的谅解和再次给予我改正错误的机会。我保证我的内容程序是自己独立完成的，绝无抄袭可能，希望老师能够相信我，给我一个机会。真的非常抱歉，再次向您道歉。保证以后不会再有这样的行为出现，也会将更多精力投入到学习中。
    </p>
    <p v-if="excType === 'encoding'">
      沈坚老师您好，我是{{ personInfo }}，非常抱歉，这次的高程作业我犯了一个非常低级的错误，我没有认真阅读材料，结果导致提交的作业编码有问题。我没有按照文档中的要求正确检查文件编码，正确安装扩展插件。是我缺乏规则意识，存在侥幸心理，因此我心甘情愿担负责任。一切规则说到底是为了让同学学到知识，因此我们保证绝对不会再有自作聪明的行为发生，我今后一定改过自新，重新审视自己对待学习的态度，上课一定专心听讲。
    </p>
  </main>
</template>
<script setup lang="ts">
import { ref } from "vue";
const excType = ref<"copy" | "beingcopied" | "format" | "encoding">("copy");
const personInfo = ref("");
const personInfo2 = ref("");
</script>
<style>
body {
  margin: 0;
}
header {
  background-color: #f0f0f0;
  padding: 2em;
  text-align: center;
  box-shadow: #0003 0 0 0 3px;
}
h1 {
  font-size: 2em;
  font-weight: bold;
  margin: 0.5em 0 0 0;
}
.about {
  margin:1.2em 0;
}
.about a{
  color:#888;
  text-decoration:none;
}
.about a:hover{
  text-decoration: underline;
  text-underline-offset: 2px;
}
.panel {
  display: flex;
  justify-content: center;
  gap: 10px;
  flex-wrap: wrap;
}
.panel input,
.panel select {
  padding: 0.4em;
  border-radius: 5px;
  background: white;
  color: black;
  font-size: 1em;
  border: #aaa 2px solid;
  outline: none;
  font-family: sans-serif;
}
main {
  max-width: 80ch;
  margin: 2em auto;
  font-size: 18px;
  line-height: 1.5;
  padding: 0 1em;
}
</style>
