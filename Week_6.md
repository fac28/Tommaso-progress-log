## Guidance
Answer the following questions considering the [learning outcomes for this week](https://learn.foundersandcoders.com/course/syllabus/developer/full-stack-app/learning-outcomes/).
Make sure to record evidence of your processes. You can use code snippets, screenshots or any other material to support your answers.

Do not fill in the feedback section. The Founders and Coders team will update this with feedback on your progress.

## Assessment
 ### 1. Show evidence of a learning outcome you have achieved this week.
**Dynamic Routing with Next.js**
 
You can change routes dynamically based on user interactions. Here's how it works based on the following snippets:
 

## File Structure

The file structure is designed to enable dynamic routing based on file and folder names. Here's a breakdown of the key files and folders:

- `LISTINGS/page.js`: This file represents the main listings page, displaying a list of items that we pass as props to the FilterAndDisplay component.


> <img src="https://github.com/fac28/Tommaso-progress-log/assets/63957194/ba7cd5f8-628d-458d-bdfb-d79afe637778" alt="Screenshot Listing" width="700">


- `COMPONENTS/FilterAndDisplay.jsx`: Here we display these items using a mapping function.
Each item gets wrapped into a Link component (line 31), which enables navigation to a dynamic route.

> <img src="https://github.com/fac28/Tommaso-progress-log/assets/63957194/bf2cee91-a7db-46bb-aa3a-4190cb1c0b7f" alt="Screenshot Listing" width="1100">

```jsx
<Link href={`/LISTING/${item.id}`}>
   {/* Your item display */}
</Link>
```

- `LISTING/[ID]/page.js`: In this file we retrieve the dynamic parameter (extracted from the URL) params.id using React's props and we display that specific image

> <img src="https://github.com/fac28/Tommaso-progress-log/assets/63957194/40bf8188-62d3-4137-be01-ac67421a906a" alt="Screenshot Listing" width="700">



 ### 2. Show an example of a learning outcome you have struggled with and/or would like to re-visit.
**Hooks**

> <img src="https://github.com/fac28/Tommaso-progress-log/assets/63957194/61f3f3d4-58d4-482d-8315-82644bac9b8d" alt="Screenshot hooks" width="700">

In this project I focused only on deployment unfortunately, so I didn' t contribute at all to the rest.
Therefore hooks such as <strong>useContext</strong>, <strong>createContext</strong> and <strong>useReducer</strong> are still stranger to me

## Feedback
### Alphonso's feedback
#### What Went Well
That is a really detailed walk through of dynamic routes! The abstraction in Next means that dynamic routes can look a little like black magic, but you've stripped down their basic workings here pretty well.

#### Even Better If
You'd probably find it really useful to narrow down your focus a bit and start off by spiking `useEffect()` a bit. Hooks come in all shapes and there are always new custome ones being made but `useEffect()` gives you all the basic syntax and will force you to think of scope in a particular way. Once you've got that down you'll see that any hook is much the same tool but perfected for a dedicated use.
