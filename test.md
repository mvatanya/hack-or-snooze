//sign up
curl -i \
     -H "Content-Type: application/json" \
     -X POST \
     -d '{"user":{"name":"Marisa Vatanya","username":"mvatanya","password":"marisa123"}}' \
      https://hack-or-snooze-v3.herokuapp.com/signup

{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6Im12YXRhbnlhIiwiaWF0IjoxNTYwNDQ2NTUwfQ.92t4WT7YeJy5Io7DjQ95futlsPC4rUqoj6DMxCmci7U",
  "user": {
    "createdAt": "2019-06-13T17:22:30.856Z",
    "favorites": [],
    "name": "Marisa Vatanya",
    "stories": [],
    "updatedAt": "2019-06-13T17:22:30.856Z",
    "username": "mvatanya"
  }
}


//posted stories
curl -i \
     -H "Content-Type: application/json" \
     -X POST \
     -d '{"token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6Im12YXRhbnlhIiwiaWF0IjoxNTYwNDQ2NTUwfQ.92t4WT7YeJy5Io7DjQ95futlsPC4rUqoj6DMxCmci7U", 
     "story": {"author":"Marisa Vatanya","title":"Test", "url": "https://www.rithmschool.com"} }' \
      https://hack-or-snooze-v3.herokuapp.com/stories

{
  "story": {
    "author": "Marisa Vatanya",
    "createdAt": "2019-06-13T17:26:30.679Z",
    "storyId": "da2dfce8-b65c-467f-967d-b35a08287997",
    "title": "Test",
    "updatedAt": "2019-06-13T17:26:30.679Z",
    "url": "https://www.rithmschool.com",
    "username": "mvatanya"
  }
}

https://hack-or-snooze-v3.herokuapp.com/stories/da2dfce8-b65c-467f-967d-b35a08287997



curl -i \
     -H "Content-Type: application/json" \
     -X POST \
     -d '{"token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6Im12YXRhbnlhIiwiaWF0IjoxNTYwNDQ2NTUwfQ.92t4WT7YeJy5Io7DjQ95futlsPC4rUqoj6DMxCmci7U"}
      https://hack-or-snooze-v3.herokuapp.com/users/mvatanya/favorites/f748a19f-f0c6-4f79-903a-b4d9ae617e61



curl -i \
     -H "Content-Type: application/json" \
     -X POST \
     -d '{"token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6Im12YXRhbnlhIiwiaWF0IjoxNTYwNDQ2NTUwfQ.92t4WT7YeJy5Io7DjQ95futlsPC4rUqoj6DMxCmci7U"} }' \
      https://hack-or-snooze-v3.herokuapp.com/users/mvatanya/favorites/f748a19f-f0c6-4f79-903a-b4d9ae617e61





      static async removeFromFavorites(username, storyID) {
    //TODO: Get API call to remove story from favorites list
    await axios.delete(`${BASE_URL}/users/${username}/favorites/${storyID}`, {
      token: "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6Im12YXRhbnlhIiwiaWF0IjoxNTYwNDQ2NTUwfQ.92t4WT7YeJy5Io7DjQ95futlsPC4rUqoj6DMxCmci7U",
    });
  }


  else {
      //removeFavoriteFromHtml(selectedStoryID);
      await User.removeFromFavorites(currentUser.username,selectedStoryID);
    }

    function removeFavoriteFromHtml(liElementID){
    for (let i = 0; i < $('#favorited-articles')[0].children.length; i++){
      if (liElementID === $('#favorited-articles')[0].children[i].id){
        $('#favorited-articles')[0].children[i].remove();
      }
    }

  }