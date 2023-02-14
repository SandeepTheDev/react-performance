> Not doing stuff is way faster than doing stuff. (**Component hierarchy & state management**)
>
> Checking to see if you can skip doing stuff is sometimes less work than doing stuff. (**Memoization**)
>
> Sometimes you can put off doing stuff. (**Suspense API**)
>
> Maybe you do the urgent stuff now and then less urgent stuff later? (**Transition API**)
>
> Always ship react app in **production mode**, always add **key** to each child in a list.

# How react actually works?

React rendering cycle can be divided into three following phases..

### Render phase

Whenever the state of application changed React create a Virtual DOM with updated state and compares it with previous Virtual DOM and calculate the changes that needs to be commited to the DOM this process is known as diffing.

### Commit phase

During this phase React commit the calculated changes to the real DOM. **Refs** also gets updated during this phase **ref always points the same object between render phase and commit phase**.

### Clean up phase

This the last step where clean up occurs.

> The only thing that cause re-render is whenever the state changed.
>
> between commit phase and clean up phase useEffect happens..

## An analogy: Render tree

Whenever the state of some component gets changed React re-render all childs down the tree **so its not always better to put all the state at the very top level**.

![Render tree](https://github.com/SandeepTheDev/react-performance/blob/main/assets/render-tree.svg)

> Stop the flow of re-rendering the tree by using the memoization but also don't do it at very beneath of the tree as it is not worthy do cost benefit analysis first before memoization.
