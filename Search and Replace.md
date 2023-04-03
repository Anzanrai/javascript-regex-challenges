###Search and Replace

Perform a search and replace on the sentence using the arguments provided and return the new sentence.

First argument is the sentence to perform the search and replace on.

Second argument is the word that you will be replacing (before).

Third argument is what you will be replacing the second argument with (after).

**Note**: Preserve the case of the first character in the original word when you are replacing it. For example if you mean to replace the word Book with the word dog, it should be replaced as Dog


```
function myReplace(str, before, after) {
  let smallAlphas = /^[a-z]/;
  let capitalAlphas = /^[A-Z]/;
  if(smallAlphas.test(before)){
    if(!smallAlphas.test(after)){
      after = after.replace(capitalAlphas, String.fromCharCode(after.charCodeAt(0) + 32));
    }
  }
  if(capitalAlphas.test(before)){
    if(!capitalAlphas.test(after)){
      after = after.replace(smallAlphas, String.fromCharCode(after.charCodeAt(0) - 32));
    }
  }
  return str.replace(before, after);
}

console.log(myReplace("He is Sleeping on the couch", "Sleeping", "sitting"));
```
