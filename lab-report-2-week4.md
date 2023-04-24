# Lab Report 2 - Servers and Bugs
In this report, we will explore some interesting things about servers, URL, and debug.

## Part 1: Write a web server and have fun with it
We will write a web server called StringServer that supports the path and behavior described in the write-up.

The request looks like:

 `/add-message?s=<string>`
 
So, for example, after

`/add-message?s=Hello`
The page should show

<img width="495" alt="Hello" src="https://user-images.githubusercontent.com/129908756/233901999-7aa21b89-c470-40b0-9250-124fcd01b50e.png">

and after `/add-message?s=How are you`

the page should show:

<img width="515" alt="How are you" src="https://user-images.githubusercontent.com/129908756/233902167-4225d39b-0969-4d04-b858-0edd279ebf06.png">

Here are my code of implemation:

Note: The `server.java` (the first two images) is the same file that we did in the lab. I worte `StringServer.java` based on the file `NumberServer.java` in the lab. As you can
see, unlike the `NumberServer.java` in the lab, I did not check so many exceptions or potential error cases in my code. This is because that I know exactly what will be typed in my server. That is I am the only user in this server. As long as I can make sure I can give correct input, thus I did not check so many exceptions and potential errors.

![29691682312411_ pic_hd](https://user-images.githubusercontent.com/129908756/233903913-29eecfe0-c6f2-45d7-8d92-075340bf4828.jpg)
![29651682311735_ pic_hd](https://user-images.githubusercontent.com/129908756/233902667-8a073380-381f-4d76-a61e-e98c1e637725.jpg)
![29661682311770_ pic_hd](https://user-images.githubusercontent.com/129908756/233902683-758c5b28-1623-4fd5-9cd8-b7696b593290.jpg)

Explanation: 

`/add-message?s=Hello`:

1. The `handleRequest` method in the report class is called. It takes the URL parameter as the input for the request information, which is URI `url`: The URL of the request, which is `/add-message?s=Hello` in this case. Then we use `getPath()` and `getQuery()` to filter the information that we are interested in. Note that we need the info after `"s="`, thus we need to `substring()` to get our desired information. After getting this information, we store it in the string variable `information`

2. relevant arguments: `URI url`: `/add-message?s=Hello`(request information)

   relevant fields of the class: `String information`: the one that we will accumulate the information, and it is empty by initialization.
   
3. Changes in the relevant fields after this request:

   `String information`: It becomes `"Hello\n" with a newline character`.

`/add-message?s=How%20are%20you`

1. We will also call `handleRequest`, but now with argument `/add-message?s=How%20are%20you`. Then, the following logic is same as above.

2. relevant arguments: `URI url`: `/add-message?s=How%20are%20you`

   relevant fields: `String information`: Now, it is `"Hello\n"` after our first call.
   
3. Changes in the relevant fields after this request:

   `String information`: It will accumalate after the first call, now it is: `"Hello\nHow are you\n"`.
   
## Part 2: Fix Bugs
Bugs I choose from the lab:
![29701682318612_ pic](https://user-images.githubusercontent.com/129908756/233919151-57cdc0cb-748b-41cb-aebc-de4f46d9a91f.jpg)

* A failure-inducing input for the buggy program:  
  JUnit test:
```
  @Test
  
  public void testReversed() {
  
    int[] input1 = { 1,2 };
    
    assertArrayEquals(new int[]{2, 1 }, ArrayExamples.reversed(input1));
    
   }
 ```
  
  Failure information on VSCode:
  ![29731682319099_ pic_hd](https://user-images.githubusercontent.com/129908756/233920573-f369acfd-b5c0-4af0-b4f5-d4cedccd59dd.jpg)

* An input that doesn’t induce a failure
  JUnit test:
```
  @Test
  
  public void testReversed() {
  
    int[] input2 = { };
    
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input2));
    
  }
```
  
  Information on VSCode:
  ![29741682319239_ pic](https://user-images.githubusercontent.com/129908756/233921164-62a9a96c-aa73-47d4-b1af-b0c2c3e5e22f.jpg)

* Bug code:

```
static int[] reversed(int[] arr) {

    int[] newArray = new int[arr.length];
    
    for(int i = 0; i < arr.length; i += 1) {
    
      arr[i] = newArray[arr.length - i - 1];
    }
    
    return arr;
}
```

Fix bug:

```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```
Why does this fix the bug?

The code inside the  for loop has bugs. Instead of using `arr[i] = newArray[arr.length - i - 1]`, we should change it to `newArray[i] = arr[arr.length - i - 1]`. The assignments are reversed. If we keeps the bugs, it will mess up the reverse method for each iteration in the for loop. If we use `newArray[i] = arr[arr.length - i - 1]`, we will successfully accomplish the reverse goal by reordering the elements.

## Part 3: Reflection

During these weeks, I think the most interessting knowledge that I have leanrned about is URL and server. I had no ideas about how these things work, even though I use them every day. Before I learned this in class, I though these knowledge are too fancy and chanllenging, and only some experts can know them well. After Professor Politz talked these things in lectures, I realize that it is quite fun to learn these and try them out in the lab. Now, I am able to make on own server and URL. Also, I have a deeper understanding about bugs. Previously, I thought that the only thing I needed to do was just to fix bugs. However, I did not have a deep understanding about bugs, like different types of bugs, sympotoms, techniques to fix bugs, etc. Now, I improved my skill of debugging! ✌🏻 
