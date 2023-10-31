## Guidance
Answer the following questions considering the [learning outcomes for this week](https://learn.foundersandcoders.com/course/syllabus/developer/full-stack-app/learning-outcomes/).
Make sure to record evidence of your processes. You can use code snippets, screenshots or any other material to support your answers.

Do not fill in the feedback section. The Founders and Coders team will update this with feedback on your progress.

## Assessment
 ### 1. Show evidence of a learning outcome you have achieved this week.
> **Dynamic Routing with Next.js**
 
You can change routes dynamically based on user interactions. Here's how it works based on the following snippet:

> 

## File Structure

The file structure is designed to enable dynamic routing based on file and folder names. Here's a breakdown of the key files and folders:

- `LISTINGS/page.js`: This file represents the main listings page, displaying a list of items.

- `LISTING/[ID]/page.js`: This file uses square brackets `[ID]` to create a dynamic route. It can match any value in the URL as an `ID` parameter. For example, accessing `/LISTING/123` will match `123` as the `ID` parameter. This dynamic value can be accessed in your code.


### Listings Page

In the `LISTINGS/page.js` file, a list of items is displayed. Each item likely has a link to its individual details page. To navigate to the dynamic route, use Next.js's `Link` component.

```jsx
<Link href={`/LISTING/${item.id}`}>
   {/* Your item display */}
</Link>
```

Product Details Page
In the LISTING/[ID]/page.js file, you retrieve the dynamic parameter, typically named id. This parameter corresponds to the value extracted from the URL. You can use this value to fetch and display the details of the specific product with that ID.

jsx
Copy code
const id = params.id
const product = getProductById(id)
By following this structure and using Next.js's dynamic routing capabilities, you can change routes based on user interactions. When a user clicks on a product in the listings, they are taken to the dynamic [ID] route, and the specific product details are displayed.


 ### 2. Show an example of a learning outcome you have struggled with and/or would like to re-visit.
> [**Learning outcome...**]  
> [your evidence here]

## Feedback
> [**Course Facilitator name**]  
> [*What went well*]  
> [*Even better if*]
