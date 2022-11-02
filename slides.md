---
# try also 'default' to start simple
theme: seriph
# title of your slide, will auto infer from the first header if not specified
title: 'React - Andrea Tosatto'
# titleTemplate for the webpage, `%s` will be replaced by the page's title
titleTemplate: 'React - Andrea Tosatto'
# favicon, can be a local file path or URL
favicon: ./assets/react-icon.svg
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: ./assets/react-icon.svg
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## React basic
  Introduction to React by Andrea Tosatto
# persist drawings in exports and build
drawings:
  persist: false
# use UnoCSS (experimental)
css: unocss
---


<div class="absolute left-385px bottom-435px">
  <h2>Andrea Tosatto</h2>
</div>

<div class="absolute left-420px bottom-220px">
  <h1> React </h1>
</div>

<div class="absolute left-340px bottom-90px">
  <a href="https://react-basic-thecmmbay.tosat.to">https://react-basic-thecmmbay.tosat.to</a>
</div>

---
layout: center
class: text-center
---
# React?

<br>
<br>

<h2><u>Libreria</u> <u>Javascript</u> per la creazione di <u>Web UI</u> <u>dinamiche</u></h2>


<!--
You can have `style` tag in markdown to override the style for the current page.
Learn more: https://sli.dev/guide/syntax#embedded-styles
-->

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---
layout: center
class: text-center
---
# Maggio 2013

[Why did we build React?](https://reactjs.org/blog/2013/06/05/why-react.html)

<br>
<br>

# Marzo 2015
[Introducing React Native](https://reactjs.org/blog/2015/03/26/introducing-react-native.html)

<br>
<br>

# Febbraio 2019
[React v16.8: The One With Hooks](https://reactjs.org/blog/2019/02/06/react-v16.8.0.html)

<br>
<br>

# Marzo 2022
[React v18.0](https://reactjs.org/blog/2022/03/29/react-v18.html)

---
layout: center
class: text-center
---
# React in un minuto

<iframe height="400px" width="800px"  scrolling="no" title="Untitled" src="https://codepen.io/andtos90/embed/LYrVKOy?default-tab=result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/andtos90/pen/LYrVKOy">
  Untitled</a> by Andrea Tosatto (<a href="https://codepen.io/andtos90">@andtos90</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>

---

# Come iniziare

<div grid="~ cols-2 gap-4">
<div>
```html {all|4-5|8-15|17-18|all|none}
<!-- index.html -->
<body>
  <h2>React in un minuto</h2>
  <div id="like-button-root"></div>

<script src=
"http://unpkg.com/react@18/umd/react.development.js">
</script>

<script src="
http://unpkg.com/react-dom@18/umd/react-dom.development.js
">
</script>

  <!-- Load your React component. -->
  <script src="like-button.js"></script>
</body>
```
</div>

<div>

```js {none|all|17-19|3-15|6-14|4|10-14|6-8|all}
// like-button.js

function LikeButton() {
  const [liked, setLiked] = React.useState(false);

  if (liked) {
    return 'You liked this!';
  }

  return React.createElement(
    'button',
    { onClick: () => setLiked(true) },
    'Like'
  );
}

const rootNode=document.getElementById('like-button-root')
const root=ReactDOM.createRoot(rootNode);
root.render(React.createElement(LikeButton));
```
  </div>
</div>

[Add React to a Website - React Docs](https://beta.reactjs.org/learn/add-react-to-a-website)
---

# JSX - 1 

<div grid="~ cols-2 gap-4">
<div>

```js {all|10-14}
// like-button.js

function LikeButton() {
  const [liked, setLiked] = React.useState(false);

  if (liked) {
    return 'You liked this!';
  }

  return React.createElement(
    'button',
    { onClick: () => setLiked(true) },
    'Like'
  );
}

const rootNode=document.getElementById('like-button-root');
const root=ReactDOM.createRoot(rootNode);
root.render(React.createElement(LikeButton));
```
  </div>
  <div>

```js {all|10-14}
// like-button.js

function LikeButton() {
  const [liked, setLiked] = React.useState(false);

  if (liked) {
    return 'You liked this!';
  }

  return (
    <button onClick={() => setLiked(true)}>
      Like
    </button>
  );
}

const rootNode=document.getElementById('like-button-root');
const root=ReactDOM.createRoot(rootNode);
root.render(React.createElement(LikeButton));
```
  </div>
</div>

[Try JSX - React Docs](https://beta.reactjs.org/learn/add-react-to-a-website#try-jsx)<br>
[Writing Markup with JSX - React Docs](https://beta.reactjs.org/learn/writing-markup-with-jsx)
---

# JSX - 2

<div id="wrap">
  <iframe id="scaled-frame" src="https://transform.tools/html-to-jsx"></iframe>
</div>

<style>
#wrap {
  width: 900px;
  height: 400px;
  padding: 0;
  overflow: hidden;
}

#scaled-frame {
  width: 1800px;
  height: 800px;
  border: 0px;
}

#scaled-frame {
  zoom: 0.5;
  -moz-transform: scale(0.5);
  -moz-transform-origin: 0 0;
  -o-transform: scale(0.5);
  -o-transform-origin: 0 0;
  -webkit-transform: scale(0.5);
  -webkit-transform-origin: 0 0;
}

@media screen and (-webkit-min-device-pixel-ratio:0) {
  #scaled-frame {
    zoom: 1;
  }
}
</style>

---

# Componenti - Riutilizzo

<div grid="~ cols-2 gap-4">
<div>

```js {all|2,6,11,18-19}
// like-button.js
function LikeButton({ title }) {
  const [liked, setLiked] = React.useState(false);

  if (liked) {
    return 'You liked ' + title;
  }

  return (
    <button onClick={() => setLiked(true)}>
      Like {title}
    </button>
  );
}
const rootNode=document.getElementById('like-button-root');
const root=ReactDOM.createRoot(rootNode);
root.render(<>
    <LikeButton title={"React"} />
    <LikeButton title={"Angular"} />
  </>);
```
</div>
  <div>
  <br>
  <iframe height="250" width="420" scrolling="no" title="Untitled" src="https://codepen.io/andtos90/embed/ZERbzXq?default-tab=result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/andtos90/pen/ZERbzXq">
  Untitled</a> by Andrea Tosatto (<a href="https://codepen.io/andtos90">@andtos90</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>
    </div>
</div>

[Your First Component - React Docs](https://beta.reactjs.org/learn/your-first-component)
---

# Componenti - Liste

<div grid="~ cols-2 gap-4">
<div>

```js {all|1|3-6|10-16}
import LikeButton from "./like-button.js"

const thingsToLike = ["React", "Angular", "Vue", "Solid"];

const rootNode=document.getElementById("like-button-root")
const root=ReactDOM.createRoot(rootNode);
root.render(
  <>
    {thingsToLike.map((title) => (
      <LikeButton title={title} />
    ))}
  </>
);
```
</div>
  <div>
  <br>
  <iframe height="250" width="420" scrolling="no" title="Untitled" src="https://codepen.io/andtos90/embed/oNyjNbY?default-tab=result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/andtos90/pen/oNyjNbY">
  Componenti - 1</a> by Andrea Tosatto (<a href="https://codepen.io/andtos90">@andtos90</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>
    </div>
</div>

[Rendering Lists](https://beta.reactjs.org/learn/rendering-lists)
---

# Props e State

```js {all|1,5,10,17,18|2,4,9}
function LikeButton({ title }) {
  const [liked, setLiked] = React.useState(false);

  if (liked) {
    return 'You liked ' + title;
  }

  return (
    <button onClick={() => setLiked(true)}>
      Like {title}
    </button>
  );
}
const rootNode=document.getElementById('like-button-root');
const root=ReactDOM.createRoot(rootNode);
root.render(<>
    <LikeButton title={"React"} />
    <LikeButton title={"Angular"} />
  </>);
```

[How declarative UI compares to imperative - React Docs](https://beta.reactjs.org/learn/reacting-to-input-with-state#how-declarative-ui-compares-to-imperative)
---

# Condividere lo stato - esempio

<iframe height="900" style="width: 800px;" scrolling="no" title="Componenti - 2" src="https://codepen.io/andtos90/embed/eYKpQPN?default-tab=result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/andtos90/pen/eYKpQPN">
  Componenti - 2</a> by Andrea Tosatto (<a href="https://codepen.io/andtos90">@andtos90</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>

---

# Condividere lo stato

<div grid="~ cols-2 gap-4">
<div>

```js {all}
function LikeButton({ title }) {
  const [liked, setLiked] = React.useState(false);

  if (liked) { return 'You liked ' + title; }
  return (
    <button onClick={() => setLiked(true)}>
      Like {title}
    </button>
  );
}

root.render(<>
    <LikeButton title={"React"} />
    <LikeButton title={"Angular"} />
    <LikeButton title={"Vue"} />
    <LikeButton title={"Solid"} />
  </>);
```
  </div>
  <div>

```js {all|1|1-8|11-24|12,16-20|12-21|all}
function LikeButton({ title, isLiked, onLike }) {
  if (isLiked) { return 'You liked ' + title; }
  return (
    <button onClick={() => onLike()}>
      Like {title}
    </button>
  );
}

const thingsToLike = ["React", "Angular", "Vue", "Solid"];
function LikeList() {
  const [liked, setLiked] = React.useState([]);
  return <>
    Number of likes: {liked.length}
    {thingsToLike.map((title) => (
      <LikeButton 
        title={title} 
        isLiked={liked.includes(title)} 
        onLike={() => setLiked([...liked, title])}
      />
    ))}
  </>
}
root.render(<LikeList />;
```
  </div>
</div>

---

# Prop drilling 

<div grid="~ cols-2 gap-4">
<div>

```js {all|18,21,5,9,1,2}
function LikeButton({ title, isLiked, onLike }) {
  if (isLiked) { return 'You liked ' + title; }
  //...//
}
function LikeList({ liked, setLiked }) {
  return thingsToLike.map((title) => (
    <LikeButton
      title={title}
      isLiked={liked.includes(title)}
      onLike={() => setLiked([...liked, title])}
    />
  ));
}
function LikeHeader({ liked }) {
  return (<div>Number of likes: {liked.length}</div>);
}
function LikeDashboard() {
  const [liked, setLiked] = React.useState([]);
  return (<>
            <LikeHeader liked={liked}/>
            <LikeList liked={liked} setLiked={setLiked}/>
          </>);
}
root.render(<LikeDashboard />);
```
  </div>
  <div>
  <br>
  <br>
  <br>
  <iframe height="250" width="420" scrolling="no" title="Condividere lo stato" src="https://codepen.io/andtos90/embed/jOKbXzq?default-tab=result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/andtos90/pen/jOKbXzq">
  Condividere lo stato</a> by Andrea Tosatto (<a href="https://codepen.io/andtos90">@andtos90</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>
  </div>
</div>

---

# Context - Confronto prima e dopo

<div grid="~ cols-2 gap-4">
<div>

```js {all}
function LikeButton({ title, isLiked, onLike }) {
  if (isLiked) { return 'You liked ' + title; }
  //...//
}
function LikeList({ liked, setLiked }) {
  return thingsToLike.map((title) => (
    <LikeButton
      title={title}
      isLiked={liked.includes(title)}
      onLike={() => setLiked([...liked, title])}
    />
  ));
}
function LikeHeader({ liked }) {
  return (<div>Number of likes: {liked.length}</div>);
}
function LikeDashboard() {
  const [liked, setLiked] = React.useState([]);
  return (<>
            <LikeHeader liked={liked}/>
            <LikeList liked={liked} setLiked={setLiked}/>
          </>);
}
root.render(<LikeDashboard />);
```
  </div>
  <div>

```js {all|1,9,10,13,19,20|1,-3,8,13-16,18-21|all}
function LikeButton({ title }) {
  const { getIsLiked, setLiked } 
        = React.useContext(LikeContext);
  if (getIsLiked(title)) { return 'You liked ' + title; }
  return (<button onClick={() => setLiked(title)}>
            Like {title}
          </button>);
}
function LikeList() {
  return thingsToLike.map((title) => (<LikeButton/>));
}

function LikeHeader() {
  const { liked } = React.useContext(LikeContext);
  return (<div>Number of likes: {liked.length}</div>);
}
function LikeDashboard() {
  return (<LikeProvider>
            <LikeHeader/>
            <LikeList/>
          </LikeProvider>);
}
root.render(<LikeDashboard />);
```
  </div>
</div>

---

# Context - Provider

<div grid="~ cols-2 gap-4">
<div>

```js {all|1,3|3-16|4,7-11|all}
const LikeContext = React.createContext([]);

function LikeProvider({ children }) {
  const [liked, setLiked] = React.useState([]);
  return (
    <LikeContext.Provider
      value={{
        liked: liked,
        setLiked: (title) => setLiked([...liked, title]),
        getIsLiked: (title) => liked.includes(title)
      }}
    >
      {children}
    </LikeContext.Provider>
  );
}
```
  </div>
  <div>

```js {all}
function LikeButton({ title }) {
  const { getIsLiked, setLiked } 
        = React.useContext(LikeContext);
  if (getIsLiked(title)) { return 'You liked ' + title; }
  return (<button onClick={() => setLiked(title)}>
            Like {title}
          </button>);
}
function LikeList() {
  return thingsToLike.map((title) => (<LikeButton/>));
}

function LikeHeader() {
  const { liked } = React.useContext(LikeContext);
  return (<div>Number of likes: {liked.length}</div>);
}
function LikeDashboard() {
  return (<LikeProvider>
            <LikeHeader/>
            <LikeList/>
          </LikeProvider>);
}
root.render(<LikeDashboard />);
```
  </div>
</div>


---

# Context - Esempio

<br>
<iframe height="400" width="900" scrolling="no" title="Context" src="https://codepen.io/andtos90/embed/Vwdezrd?default-tab=result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/andtos90/pen/Vwdezrd">
  Context</a> by Andrea Tosatto (<a href="https://codepen.io/andtos90">@andtos90</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>

---

# Context - Pro e Contro

<br>
<br>

## PRO

- Facile da utilizzare
- Integrato in React

## Contro

- Non adatto ad applicazioni con frequenti aggiornamenti
- Le logiche complesse vanno gestite con molta attenzione per evitare esplosione di useState

---

# Librerie di state management

- React API (Context, State, Reducer)
- Flux (Redux, Zustand)
- Proxy (Mobx, Valtio)
- Atomic (Recoil, Jotai)
- Data Fetching (React query, SWR)
- ...
- Combinazione di una o più librerie

<br>
<br>
<br>

<hr/>

- [Choosing the right React state management - LogRocket Blog](https://blog.logrocket.com/guide-choosing-right-react-state-management-solution/)
- [Top 6 React State Management - OpenReplay Blog](https://blog.openreplay.com/top-6-react-state-management-libraries-for-2022/)
- [Jotai vs Recoil - LogRocket Blog](https://blog.logrocket.com/jotai-vs-recoil-what-are-the-differences/)

---
layout: center
class: text-center
---

# Grazie!

[React Beta Docs](https://beta.reactjs.org/)
