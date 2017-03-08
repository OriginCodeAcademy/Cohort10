# Origin Message Board

If you look up at the projector, you should see a browser window that has been left running, filled with the endless echoes of previous Cohorts that have attempted this exercise. (Except you guys Cohort 10 - you're the first ones. Make some noise!)

Your task is to build a website on your machine that sends messages to the website on the projector.

**Note:** When working from home, you can see the projector app by visiting [https://originmessages.herokuapp.com](https://originmessages.herokuapp.com).

## Your website should look like this
![](http://i.imgur.com/K2yxocg.png)

## Your website should post a message to the projector
The user should be able to enter some text, then once they click the `Send!` button, an HTTP POST request should be made to the API url described below.

## Your code should use `$.ajax`
When the user clicks the `Send!` button, you should use [`$.ajax`](https://api.jquery.com/jquery.ajax/) to send an object containing data to send to `http://originmessages.herokuapp.com/messages`;

**Important:** You will need to set the `contentType` to `application/json` when calling `$.ajax`.

Here is an _example_ snippet of code.

```js
let message = {
  username: 'Cameron',
  message: 'Looks like somebody is running the sample!'
};

// Write your Ajax code here :)
```

## It should show up on the projector if HTTP POST request was successsful
You can verify that you've finished when you are able to see your message up on the projector.

## Turn In Instructions
* Push your changes to GitHub.
* [Click here to create an issue in the class repository](https://www.github.com/OriginCodeAcademy/Cohort10/issues/new?title=05-OriginMessageBoard&body=1.%20Where%20can%20I%20find%20your%20repository%3F%20(Paste%20the%20url%20of%20your%20repository%20below)%0A%0A2.%20What%20is%20an%20HTTP%20POST%20request%3F%0A%0A3.%20What%20is%20an%20HTTP%20GET%20request%3F)
    * Include a link to your repository in the description
    * Answer the questions filled out for you in the description
