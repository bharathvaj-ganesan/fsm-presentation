---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: false
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# some information about the slides, markdown enabled
info: |
  ## Building better UI with Finite Automata
---

<div class="text-left">
  <h1>Building Better UI <br>with<div class="text-red-500">Finite Automata</div></h1>
  <a href="https://twitter.com/bharathvaj_g">@bharathvaj_g</a>
</div>

<a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub"
  class="abs-br m-6 text-xl icon-btn opacity-50 !border-none !hover:text-white">
  <carbon-logo-github />
</a>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---

<div class="flex justify-center flex-col items-center h-100">
  <h1>Developing user interfaces <span class="text-red-500">is not easy</span></h1>

  <img class="mt-4" width="300" src="https://i.redd.it/hixi2erwagxy.gif" />

</div>


---

<div class="flex justify-center flex-col items-center text-center h-100">
  <h1>Deterministic Finite Automata<div class="text-red-500">(Finite State Machines)</div></h1>
</div>

---

<div class="flex justify-center flex-col items-center h-100">
  
  <blockquote>
    <h1>Finite State Machine is an important 16 mark question</h1>
    <cite class="text-red-500 block text-right">-- College Professor</cite>
  </blockquote>

</div>

---

# Automata theory

* Combinatorial logic
* <span class="text-red-800">Finite state machines</span>
* Pushdown automata
* Turing machines


<img class="float-right abs-br m-6" width="500" src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a2/Automata_theory.svg/1600px-Automata_theory.svg.png">

---

# What is a state machine?

<div class="mt-8">
  <a href="https://en.wikipedia.org/wiki/Finite-state_machine">Definition from Wikipedia</a>

  <blockquote class="mt-6">
    an abstract machine that can be in exactly one of a finite number of states at any given time. The FSM can change from one state to another in response to some external inputs; the change from one state to another is called a transition. An FSM is defined by a list of its states, its initial state, and the conditions for each transition.
  </blockquote>

  And further: 
  
  <blockquote class="mt-4">
    A state is a description of the status of a system that is waiting to execute a transition.
  </blockquote>

</div>

---

<div class="flex justify-center flex-col items-center h-100 text-center">
  <div>
    <img class="m-auto" height="300" width="400" src="http://web.mit.edu/2.744/studentSubmissions/humanUseAnalysis/keval/vm.jpg">
    <div class="mt-4">Start -> Select Shelf -> Money -> More money (if not enough) -> Dispatch Snacks</div>
  </div>
</div>


---
layout: center
class: text-center
---

<h1>Time for demo</h1>

---
layout: center
class: text-center
---

<h1>🍑🆙<br/><span class="text-red-500">Bottom-up </span>approach</h1>

---

# Challenges

<li v-click>Difficult to understand</li>
<li v-click>Will contain bugs</li>
<li v-click>Difficult to test</li>
<li v-click>Difficult to enhance</li>
<li v-click>Features make it worse</li>

<v-click>
  <img class="float-right abs-br m-6" width="600" src="/bool.png" >
</v-click>

---
layout: center
class: text-center
---

<h1>User interfaces are <span v-click class="text-red-500">graphs</span></h1>

---
layout: center
class: text-center
---

<h1><span class="text-red-500">Designing</span> state machines</h1>

---
layout: center
class: text-center
---

<h1>Time for another viz demo using <span class="text-red-500">XSTATE</span></h1>

---

# States of Matter: <span class="text-red-500">Water</span>
<div class="flex justify-center flex-col items-center h-100">
  <img width="500" src="https://raw.githubusercontent.com/jakesgordon/javascript-state-machine/master/examples/matter.png">
</div>

---

# Water Machine

```ts
const waterMachine = Machine({
  id: 'water',
  initial: 'solid',
  states: {
    solid: {
      on: {
        MELT: 'liquid'
      }
    },
    liquid: {
      on: {
        VAPORIZE: 'gas',
        FREEZE: 'solid'
      }
    },
    gas: {
      on: {
        CONDENSE: 'liquid'
      }
    }
  }
});
```
---
layout: center
class: text-center
---

<h1>
  <span class="text-red-500">Developing</span> with state machines
  <h2>using <span class="text-red-500">XSTATE</span></h2>
</h1>


---
layout: center
class: text-center
---

<h1><span class="text-red-500">Major challenge</span> with FSMs</h1>

---
layout: center
class: text-center
---

# Traffic Light

<img width="500" src="/light.png">

---
layout: center
class: text-center
---
# State <span class="text-red-500">Explosion</span>

<img width="500" src="/light-bomb.png">

<a href="https://statecharts.dev/state-machine-state-explosion.html">Another Example</a>

---
layout: center
class: text-center
---

<h1>
<div class="text-red-500">Statecharts</div>
Hierarchical finite state machines
</h1>

---
layout: center
class: text-center
---

# Hierarchical (Nested) State Machines

<img width="400" src="/light-heir.png">

---
layout: center
class: text-center
---

# Parallel State Machines

<div class="flex">
  <div class="flex items-center"><img width="400" height="300" src="/concurrent_ui.gif"></div>
  <img width="400" src="https://imgur.com/GKd4HwR.png">
</div>

---
layout: center
class: text-center
---

# History States

<img width="400" src="https://imgur.com/I4QsQsz.png">

---

# Resources

* https://xstate.js.org/
* https://statecharts.dev/
* https://dev.to/davidkpiano/no-disabling-a-button-is-not-app-logic-598i
* https://sketch.systems/
* http://www.inf.ed.ac.uk/teaching/courses/seoc/2005_2006/resources/statecharts.pdf
* https://rauchg.com/2015/pure-ui
* https://medium.com/@asolove/pure-ui-control-ac8d1be97a8d
* https://www.youtube.com/watch?v=tpNmPKjPSFQ


---
layout: center
class: text-center
---

# Q&A

<img src="https://image.shutterstock.com/image-illustration/road-sign-used-us-state-260nw-390622564.jpg">