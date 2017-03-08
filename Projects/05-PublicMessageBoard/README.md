# Public Message Board

If you look up at the projector, you will see a browser window that has been left running.

Your task is to build a website that allows users to post a message to the projector.

I won't go into the details of how the projector app works, instead I'd like you
to focus on building the app that sends information to the projector.

## It should look like this
![](http://i.imgur.com/K2yxocg.png)

## It should post a message to the projector
The user should be able to enter some text, then once they click the `Send!` button, an HTTP POST request should be made to the API url described below.

## It should create an HTTP POST request
When the user clicks the `Send!` button, you should use [`$.post`](https://api.jquery.com/jquery.post/) to send the text to `http://originmessages.herokuapp.com/api/message`;

Something like this:

```js
$.post('http://originmessages.herokuapp.com', 'Hey, it works!', function(data) {
  alert('Data sent to server');
})
```

## It should show up on the projector if HTTP POST request was successsful
This is really my responsibility - but you can verify you are done when you are able to see your message up on the projector.

## Turn In Instructions
* Push your changes to GitHub.
* [Click here to create an issue in the class repository](https://www.github.com/OriginCodeAcademy/Cohort10/issues/new?title=05-PublicMessageBoard&body=1.%20Where%20can%20I%20find%20your%20repository%3F%20(Paste%20the%20url%20of%20your%20repository%20below)%0A%0A2.%20What%20is%20an%20HTTP%20POST%20request%3F%0A%0A3.%20What%20is%20an%20HTTP%20GET%20request%3F)
    * Include a link to your repository in the description
    * Answer the questions filled out for you in the description
