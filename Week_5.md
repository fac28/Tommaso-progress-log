## Guidance
Answer the following questions considering the [learning outcomes for this week](https://learn.foundersandcoders.com/course/syllabus/developer/client-side-app/learning-outcomes/).
Make sure to record evidence of your processes. You can use code snippets, screenshots or any other material to support your answers.

Do not fill in the feedback section. The Founders and Coders team will update this with feedback on your progress.

## Assessment
 ### 1. Show evidence of a learning outcome you have achieved this week.
**Use JSX to create DOM elements**  
> <img src="https://github.com/fac28/Tommaso-progress-log/assets/63957194/c615171d-e04c-4935-b9af-acb0962262b6" alt="Screenshot component" width="500">
 
  Here we create a component called PlayerBoard that renders a 2d grid based on an array we passed as props (<strong>board</strong>) 

**Use component state to manage DOM updates**
> <img src="https://github.com/fac28/Tommaso-progress-log/assets/63957194/dc4bb182-1d5f-46ac-a10a-3a158a7863d4" alt="Screenshot change State" width="500">

-  <strong>playerBoard</strong> is a state variable created using the <strong>useState</strong> hook. It represents a 2D array (a grid) that contains information  about the player's game board, with all values set to null using Array.from.

-  Once ships are placed onto it using the <strong>placeShip</strong> function, <strong>[...playerBoard]</strong> creates a new array that is a shallow copy of the <strong>playerBoard</strong> array. Shallow copy means that the new array is a new object, but the elements inside it (in this case, the rows of the 2D array) are still references to the same objects in memory as the original <strong>playerBoard</strong>.

-  <strong>setPlayerBoard([...playerBoard])</strong> is then used to update the state. It's important to note that in React, you should not mutate state directly, so you create a new array (shallow copy) and update the state with that new array. React will then trigger a re-render of the component with the updated state.

-  So, when <strong>setPlayerBoard([...playerBoard])</strong> is called, it effectively sets the <strong>playerBoard</strong> state to a new array that is a copy of the previous <strong>playerBoard</strong>, ensuring that state changes are properly managed in a React component. Any changes made to this new array won't affect the original <strong>playerBoard</strong> state, which is essential for React's state management and rendering updates.




 








 ### 2. Show an example of a learning outcome you have struggled with and/or would like to re-visit.
> [**Learning outcome...**]  
> The fact we used a generated array that way is quite confusing to be honest.I also find the whole React concept still not easy to fully understand. Having only 2 days to complete the project made us rush a lot, I' m pretty sure there is a better way to structure and write the whole app in terms of components and logic behind it

## Feedback
> [**Course Facilitator name**]  
> [*What went well*]  
> [*Even better if*]
