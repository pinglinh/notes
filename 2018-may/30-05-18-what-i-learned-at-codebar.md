## Docker

Today at codebar I learned that Docker helps to eliminate the different versioning of software such as node.js or npm when the code is being pushed to different servers. For example, your code may work locally on your machine however when it's being pushed to a remote server it may not work due to different versions of dependencies. With docker, you can make an image of your current setup so that when it runs in a different server it will have the same dependencies. This will also avoid any errors that may stem from the different versions of dependencies between the server and your own local machine.

Also had a go at using travis for CI. It was nice but scary at the same time how it just did everything for you with a very simple yml config. Need to try out other CI tools.
