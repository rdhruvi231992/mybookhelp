# mybookhelp

NOTE: If your run into issues installing the dependencies with NPM, use this command:
# Install dependencies with all permissions
$ sudo npm install --unsafe-perm=true --allow-root
Once your server has started, go to this url http://localhost:8000/ and you will see the website running on a Development Server:
Create a New React App




Create React App is a comfortable environment for learning React, and is the best way to start building a new single-page application in React.

npx create-react-app my-app
cd my-app
npm start




🔍 Problem
You want to get started in building React apps.
💡 Approach
Use CRA to start a new app.
npx create-react-app my-app
cd my-app
npm start

Navigate your browser to http://localhost:3000.
Open an editor in the new project.
code .

Create a new component called Title in ./src/Counter.js
import React from "react"

const Title = props => {}

Add component that increments on each click, and renders clickedOnCount.
import React from "react"

const Title = props => {
    const Title = "My first component"
    return <h1>{Title}</h1>
}

Add the export keyword so we can import it in App.js
import React from "react"

export const Title = props => {
    const Title = "My first component"
    return <h1>{Title}</h1>
}

Gut out the App component in App.js
import React from "react"
import logo from "./logo.svg"
import "./App.css"
import { Counter } from "./Counter"

function App() {
    return <div className="App"></div>
}
export default App

Import Title in and use it inside the App component.
import React from "react"
import logo from "./logo.svg"
import "./App.css"
import { Title } from "./Title"

function App() {
    return (
        <div className="App">
            <Title />
        </div>
    )
}

export default App

React Error Handling
🔍 Problem
You want to handle errors that are being thrown from downstream React components.
💡 Approach
Use error boundaries.
Create component that implements componentDidCatch.
class ErrorBoundary extends React.Component {
  constructor(props) {
    super(props);
    this.state = { hasError: false };
  }

  static getDerivedStateFromError(error) {    // Update state so the next render will show the fallback UI.    return { hasError: true };  }
  componentDidCatch(error, errorInfo) {    // You can also log the error to an error reporting service    logErrorToMyService(error, errorInfo);  }
  render() {
    if (this.state.hasError) {      // You can render any custom fallback UI      return <h1>Something went wrong.</h1>;    }
    return this.props.children;
  }
}

Wrap downstream components with ErrorBoundary.
<ErrorBoundary>
    <MyWidget />
</ErrorBoundary>

Arrow Functions
🔍 Problem
You want to write leaner functions with less ceremony.
💡 Approach
Use arrow functions.
Old way:
function helloWorld(name) {
    return "Hello " + name + "!"
}

Using arrow functions:
const helloWorld = name => {
    return "Hello " + name + "!"
}

The last line of a function implicitly returns, so you can write this in a single line:
const helloWorld = name => "Hello " + name + "!"

Template Strings
🔍 Problem
You want to build strings in a neater fashion.
💡 Approach
Old way:
const helloWorld = name => `"Hello " + name + "!"`

Use the backtick character ` rather than the usual quote marks ' or " to use template strings. Use ${var_name} to replace that part with the value of the variable.
They bring simple string interpolation to JavaScript, and are a convenient way to plug variables directly into a string.
const helloWorld = name => `Hello ${name}!`


React Stateless Components
🔍 Problem
You want to break down UI development into independent, reusable pieces.
💡 Approach
Use stateless components.
Stateless Components in React are essentially JavaScript functions.
import React, { Component } from "react"

function Hello({ name }) {
    return <h1>Hello {name}!</h1>
}

This is the stateful equivalent:
import React, { Component } from "react"

class Welcome extends Component {
    render() {
        const { name } = this.props
        return <h1>Hello {name}!</h1>
    }
}

As far as React is concerned these two examples are exactly the same.
import ReactDOM from "react-dom"

const rootNode = document.getElementById("root")
ReactDOM.render(
    <Welcome name="Alex">,
    rootNode,
)

React with component state
🔍 Problem
You need a component that "remembers" what has happened in the past, with complex business logic.
💡 Approach
Stateful components allow you to create components that have variables that persist throughout the lifecycle of the application.
There are currently two ways within React to save state. Hooks and component state. The below covers component state.
Create a stateful component with initial variable counter 0.
import React, { Component } from "react"

class StatefulCounter extends Component {
    state = { counter: 0 }
}

Add the render function and set a variable from the state
import React, { Component } from "react"

class StatefulCounter extends Component {
    state = { counter: 0 }
    render() {
        const { counter } = this.state
    }
}

Add a return statement that contains the onClick event and the rendered counter value.
import React, { Component } from "react"

class StatefulCounter extends Component {
    state = { counter: 0 }
    render() {
        const { counter } = this.state
        return <h1 onClick={() => this.setState({ counter: counter + 1 })}>Clicked {counter}!</h1>
    }
}

Stateful components have many other useful methods, some useful ones are:
componentDidMount()
componentWillUnmount()
shouldComponentUpdate()
componentDidUpdate()
You can read more at the React website.

React with hook state
🔍 Problem
You need a component that "remembers" what has happened in the past.
💡 Approach
Use CRA to start a new app.
npx create-react-app my-app
cd my-app
npm start

Navigate your browser to http://localhost:3000.
Open an editor in the new project.
code .

Create a new component called Counter in ./src/Counter.js
import React from "react"

const Counter = props => {}

Add a hook state called clickedOnCount.
import React from "react"

const Counter = props => {
    const [clickedOnCount, setClicked] = React.useState(0)
}

Add component that increments on each click, and renders clickedOnCount.
import React from "react"

const Counter = props => {
    const [clickedOnCount, setClicked] = React.useState(0)
    return <h1 onClick={() => setClicked(clickedOnCount + 1)}>I've been clicked on {clickedOnCount} times!</h1>
}

Add the export keyword so we can import it in App.js
import React from "react"

export const Counter = props => {
    const [clickedOnCount, setClicked] = React.useState(0)
    return <h1 onClick={() => setClicked(clickedOnCount + 1)}>I've been clicked on {clickedOnCount} times!</h1>
}

Gut out the App component in App.js
import React from "react"
import logo from "./logo.svg"
import "./App.css"
import { Counter } from "./Counter"

function App() {
    return <div className="App"></div>
}
export default App

Import Counter in and use it inside the App component.
import React from "react"
import logo from "./logo.svg"
import "./App.css"
import { Counter } from "./Counter"

function App() {
    return (
        <div className="App">
            <Counter />
        </div>
    )
}

export default App

















-------------------------------------


React: Creating and Hosting a Full-Stack Site

Cd my app 
Npm run build
Copy and paste build folder in backend side
(run mongo)
Npm start (server start navigate localhost 80000)
Git init(initialised empty repo)
Git status 
Create .gitignore file and write node_modules
Git add .
Git commit -m “first commit”
Got to git acc and create repo same name as app name.
Copy path from git link and run in the terminal
Now all the things on the web


Try AWS or netlify.app
----------------------------------



Prepare your programming environment
🔍 Problem
You are ready to join the Ninja Academy, or start programming on your own. You need the tooling and applications to be able to get started.
💡 Approach
Install Ubuntu
Install Docker
Install ZSH
Install oh-my-zsh
Install git
Install vscode
Install go
Install nvm
Install node using nvm
Install prettier
Setup a GitHub account
Configure Prettier
Prettier is an opinionated code formatter for JavaScript.
Create a .prettierrc file in your project:
{
    "bracketSpacing": true,
    "useTabs": true,
    "printWidth": 160,
    "singleQuote": false,
    "trailingComma": "all",
    "semi": false,
    "jsxBracketSameLine": false
}


Use WaitGroups to sync up parallel tasks
🔍 Problem
You need to do two things at once, and need to wait for both to finish before continuing on.
💡 Approach
We can use wait groups for this problem. Channel are also a possibility.
func createSession(w http.ResponseWriter, r *http.Request) {
    fn := func(w http.ResponseWriter, r *http.Request) (int, error, string) {
    wg := &sync.WaitGroup{}
    wg.Add(1)
    go func(wg *sync.WaitGroup) {
        defer wg.Done()
        err := doSomething()
        if err != nil {
            fmt.Println(err)
        }
    }(wg)
    
    // Do other stuff
    wg.Wait()
}

Use functional handlers to add parameters to your handlers
🔍 Problem
You need to inject config to use in a HTTP handler.
💡 Approach
Use functional handlers. These are functions that return a http.HandlerFunc.
Instead of
func ExampleHandler(w http.ResponseWriter, r *http.Request) {
    // Handle the function
    // It is stateless with no additional parameters
}

func ExampleHandler(config *Config) func(w http.ResponseWriter, r *http.Request) {
    fn := func(w http.ResponseWriter, r *http.Request) {
        // Handle the function
        // You now have access to the config struct
    }
    return fn
}

Now when you declare your routes, you can inject config data:
func main() {
    config := NewConfig()
    r := chi.NewRouter()
    r.Get("/", ExampleHandler(config))
}

Getting started learning
🔍 Problem
You want to become a programmer, but you are overwhelmed. Where do you start?
💡 Approach
Alex Dunmow, Ninja Software CEO, provides his perspective.
Give Yourself a Project
First step of learning how to program is to make sure there is a goal beyond "learn how to code." No one ever learns how to code, they force themselves to bash their way through achieving their goals.
For me, that was building a Quake 2 mod when I was 11. For the first few weeks I literally just copied and pasted code I didn't understand from other people's mods. I'd look at a piece of code and think "this achieves what I want... kinda" and of course it wouldn't. I had to hack my way through the confusion until I'd get a win, which sometimes took a while.
Those early wins are important though, and learning how to get unstuck is also super important.
Below are some common ideas for projects:
A video game
Some simple tools
Web development
App development
Windows Development
Data science/Machine Learning (AI)
Pick one according to your interests (not what you think is "good for your career") then build something with it.
A video game
A common desire, with tons of resources on the internet.
Some potential technologies to learn:
Unity (C#)
http://unity3d.com/learn
https://www.youtube.com/user/PushyPixels
https://www.udemy.com/course/unitycourse/ (paid)
http://www.csharpcourse.com (not Unity, but C#)
Godot (GDScript, C#)
https://www.youtube.com/watch?v=y1E_y9AIqow&feature=youtu.be
https://docs.godotengine.org/en/stable/getting_started/step_by_step/your_first_game.html
You can setup a developer account at Itch, to distribute your work.
Some simple tools
Automate something or scrape websites. Perhaps a scraping bot to read bank transactions, or maybe a cryptocurrency trading bot.
Python is a great language for learning to program for these sorts of problems.
Python for everybody
Python Principles
Learn to code with Python
Automate the Boring Stuff with Python
Web development
Best language to learn here is JavaScript. JavaScript can be used as a frontend and backend.
Some project ideas
BitDegree
Udemy
FreeCodeCamp
The Odin Project
App development
You'll need a MacOS device to do iOS development.
Older apps were made in Objective-C, which is Apple's version of Java (essentially). Modern apps are made with a language called Swift, which is closer to Python and is easier to learn.
Swift:
https://www.raywenderlich.com
https://www.hackingwithswift.com/
Android
https://developer.android.com/guide
https://www.udacity.com/course/new-android-fundamentals--ud851
Windows Development
An interesting choice. I haven't built a desktop application in years. Most development these days is web and mobile app development.
Needs to be in C# there's no other language worth learning to achieve this.
Pluralsight
Head First C#
Data science/Machine Learning (AI)
I included this here because AI is hot right now, and it's totally the future.
I would, however, strongly urge anyone away from starting with Machine Learning. Learn to code first.
Regardless, if you want to power on check out the 20 best machine learning online courses.
What do we use?
Some tech we use at Ninja Software:
Go: Google's system language, we use this for backend software
https://tour.golang.org/welcome/1
TypeScript: Microsoft's language that transpiles to JavaScript.
React: Frontend UI framework. Powers Facebook. Built using TypeScript.
https://www.udemy.com/course/react-with-typescript/
https://www.pluralsight.com/guides/typescript-react-getting-started
https://egghead.io
PostgreSQL: enterprise level database, free and open source.
Python tutorial: https://pynative.com/python-postgresql-tutorial/
Build a RESTful API with Node.js, Express and PostgreSQL: https://www.udemy.com/course/build-a-restful-api-with-nodejs-express-and-postgresql
Go tutorial: https://flaviocopes.com/golang-tutorial-rest-api/
C# tutorial: http://zetcode.com/csharp/postgresql/
Helpful Tools
VSCode: great editor, works on any OS, free: https://code.visualstudio.com
Docker: allows easy spin up of services
https://elanderson.net/2018/02/setup-postgresql-on-windows-with-docker/
https://www.youtube.com/watch?v=iJeL2tOFfvM
Getting Unstuck
Once you've started down your path and begin learning to code, some things will be quickly obvious, but others will be very difficult to understand. If you're doing this on your own you may find yourself stuck in a way that's hard to get yourself out of.
You’ll encounter trouble with simple concepts that tutorials don't even think to explain. Error messages from your compiler or webpack will baffle you.
First of all: Don't panic. Don't get angry. Don't beat yourself up. Every developer has been there at one point, and will be there again. You'll struggle to get unstuck, but after time you will get better at it, and you'll know where to turn.
Some tips:
Don't bother with books, they suck for getting unstuck
Stack Overflow is amazing
Google search error messages to help you fix them. Wrap them in "". Remember to remove information that is unique to your project.
Here's a useful tutorial on how to Google your error messages.
Always include the name or tool you're using when you search error messages. E.g: `"nil pointer dereference" golang
Avoid the XY Problem.
If you're asking people for help (maybe on StackOverflow or Discord) try to explain what you're doing in the least amount of words possible.
Join Meetups for beginners and your chosen languages, community is important
https://www.meetup.com/en-AU/topics/learn-to-code/au/perth/
https://www.meetup.com/en-AU/perth-golang-meetup/
Most importantly, don't get confused by opinionated programmers. It's inevitable that you'll tell someone that you're learning x to achieve y, and they'll say "oh, x is stupid! You should drop it and instead use z." Feel free to try z, but don't abandon everything because someone has an opinion. Figure it out yourself and don't be dissuaded by jerks.
What are you waiting for? Get yourself a goal and get to work!
-------------------------------------------------------------------------------------------------
New Go Project Spinup
🔍 Problem
You are ready to try and do some programming in Go. What to do?
💡 Approach
Create a new folder for your project.
mkdir my-project
cd my-project

Initialise the repo.
git init

Create a main.go file.
touch main.go

Initialise the go modules file.
go mod init my-project

Open the editor in the folder.
code .


 Go Basic Hello World
🔍 Problem
You want to get started in programming in Go, Google's high performance server language.
💡 Approach
Create an empty main project.
package main

func main() {
}

Print Hello World!
import (
    "fmt"
)
func main() {
    fmt.Print("Hello world!")
}

Go API Server
🔍 Problem
You need to write a simple, lean, high performance server that provides a REST API.
💡 Approach
Create your router.
package main

import (
    "fmt"
    "log"
    "net/http"
)

func main() {
    r := http.NewServeMux()
}

Add a route to the router. Select a relevant handler name as the function to execute when the router is triggered.
package main

import (
    "fmt"
    "log"
    "net/http"
)

func main() {
    r := http.NewServeMux()
    r.HandleFunc("/", IndexHandler)
}

// IndexHandler to handle requests
func IndexHandler(w http.ResponseWriter, r *http.Request) {
}

Implement handler logic.
package main

import (
    "fmt"
    "log"
    "net/http"
)

func main() {
    r := http.NewServeMux()
    r.HandleFunc("/", IndexHandler)
    log.Fatalln(http.ListenAndServe(":8080", nil))
}

// IndexHandler to handle requests
func IndexHandler(w http.ResponseWriter, r *http.Request) {
    if r.Method != "GET" {
        return
    }
    w.Write([]byte("Hello world!"))
}


Start the server with router r on port 8080.
package main

import (
    "fmt"
    "log"
    "net/http"
)

func main() {
    r := http.NewServeMux()
    r.HandleFunc("/", IndexHandler)

    fmt.Println("Starting server on port :8080")
    log.Fatalln(http.ListenAndServe(":8080", nil))
}

// IndexHandler to handle requests
func IndexHandler(w http.ResponseWriter, r *http.Request) {
    if r.Method != "GET" {
        return
    }
    fmt.Println("Received request")
    w.Write([]byte("Hello world!"))
}

Add some logging so you know when the server starts, and when a request has come in.
package main

import (
    "fmt"
    "log"
    "net/http"
)

func main() {
    r := http.NewServeMux()
    r.HandleFunc("/", IndexHandler)

    fmt.Println("Starting server on port :8080")
    log.Fatalln(http.ListenAndServe(":8080", nil))
}

// IndexHandler to handle requests
func IndexHandler(w http.ResponseWriter, r *http.Request) {
    if r.Method != "GET" {
        return
    }
    fmt.Println("Received request")
    w.Write([]byte("Hello world!"))
}

Go API Client
🔍 Problem
You need to make requests to an API server.
💡 Approach
Start with an empty main file.
package main

func main() {
}

Create a Go client.
package main

import (
    "net/http"
)

func main() {
    c := &http.Client{}
}

Build the request.
package main

import (
    "net/http"
)

func main() {
    c := &http.Client{}
    req, err := http.NewRequest("GET", "https://pokeapi.co/api/v2/pokemon/ditto", nil)
    if err != nil {
        fmt.Println(err)
    }
}

Execute the request with the client.
package main

import (
    "fmt"
    "net/http"
)

func main() {
    c := &http.Client{}
    req, err := http.NewRequest("GET", "https://pokeapi.co/api/v2/pokemon/ditto", nil)
    if err != nil {
        fmt.Println(err)
    }
    resp, err := c.Do(req)
    if err != nil {
        fmt.Println(err)
    }
}

Read the response body into a byte array.
package main

import (
    "fmt"
    "io/ioutil"
    "net/http"
)

func main() {
    c := &http.Client{}
    req, err := http.NewRequest("GET", "https://pokeapi.co/api/v2/pokemon/ditto", nil)
    if err != nil {
        fmt.Println(err)
    }
    resp, err := c.Do(req)
    if err != nil {
        fmt.Println(err)
    }
    b, err := ioutil.ReadAll(resp.Body)
    if err != nil {
        fmt.Println(err)
    }
}

Print the response.
package main

import (
    "fmt"
    "io/ioutil"
    "net/http"
)

func main() {
    c := &http.Client{}
    req, err := http.NewRequest("GET", "https://pokeapi.co/api/v2/pokemon/ditto", nil)
    if err != nil {
        fmt.Println(err)
    }
    resp, err := c.Do(req)
    if err != nil {
        fmt.Println(err)
    }
    b, err := ioutil.ReadAll(resp.Body)
    if err != nil {
        fmt.Println(err)
    }
    fmt.Println(string(b))
}

--------------------------------------------------------------------------------------------------

Containerised Services
🔍 Problem
You need to run many services such as an SQL database.
Often you would need multiple instances if you are working on multiple projects.
You want to start, stop and delete these databases without too much resource usage, and quickly.
💡 Approach
You need containers.
Follow installation instructions from the Docker webpage
sudo apt-get remove docker docker-engine docker.io containerd runc
sudo apt-get update
sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo apt-key fingerprint 0EBFCD88
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
sudo usermod -aG docker $WHOAMI

Run postgres for use with your Go apps!
docker run -d -p 5438:5432 --name postgres -e POSTGRES_USER=dev -e POSTGRES_PASSWORD=dev -e POSTGRES_DB=dev postgres:13-alpine


Go Authentication Part 1: Boilerplate
🔍 Problem
You need to control access of certain areas of the web application to certain users.
💡 Approach
Setup authentication on your server. The following actions need to be implemented:
Sign up
Sign in
Sign out
Forgot password
Reset password
Start with the empty main project.
package main

func main() {
}

Create the empty router and server.
package main

import (
    "github.com/go-chi/chi"
)

func main() {
    r := chi.NewRouter()
    log.Fatalln(http.ListenAndServe(":8080", r))
}

Create a handler for each action.
package main

import (
    "github.com/go-chi/chi"
)

func main() {
    r := chi.NewRouter()
    r.Get("/signup", SignUpHandler)

    r.Get("/signin", SignInHandler)
    r.Get("/signout", SignOutHandler)
    r.Get("/forgotpassword", ForgotPasswordHandler)
    r.Post("/resetpassword", ResetPasswordHandler)
    log.Fatalln(http.ListenAndServe(":8080", r))
}

func SignUpHandler(w http.ResponseWriter, r *http.Request) {

}

func SignInHandler(w http.ResponseWriter, r *http.Request) {

}

func SignOutHandler(w http.ResponseWriter, r *http.Request)

func ForgotPasswordHandler(w http.ResponseWriter, r *http.Request) {

}

func ResetPasswordHandler(w http.ResponseWriter, r *http.Request) {

}


Future documents will cover implementation of each handler.
Simple email validation in JavaScript
🔍 Problem
You need to ensure that an email address provided by a user is actually an email address.
💭 Thoughts
Email validation is a thorny issue. There's a huge amount of solutions for validating emails on sites like StackOverflow, and the vast majority of them will incorrectly classify real email addresses as invalid.
Using regex to validate an email address should be considered potentially harmful. Incorrect assumptions by the author of the regex will often block real users from registering to your service. The bulk of email validating regex out in the wild is likely copied from someone else's code.
An email address has two sections, a username and a domain.
The username can contain escaped characters, and "unusual" characters that regex will often consider invalid even though it's not. For example: "Martin.O'Martin@omartin.com" is a completely valid email address. Many validators will block it due to the '.
Usernames can contain an @. martin@martin@omartin.com is technically a valid email address.
The username can be case sensitive; It is very unlikely that an email server will be configured this way, however.
The domain can contain zero or more labels separated by a period (.).
Ultimately, the best way to validate an email address is to send it an email. This is why most online services will send an email doing just that.
What does this mean for you? The lone programmer building a sign up form who just wants valid emails to be entered?
It's still a good idea to test that your email address:
has a domain
has a username
that are separated by an @
💡 Approach
So let's not over think this. Here is the simplest way you can validate that the email address provided by your new user is likely valid:
const validateEmail = email => /\S+@\S+\.\S+/.test(email)

console.log(validateEmail("martin.o'martin@example.com"))

Good enough! Now properly validate that address by sending it an email.
Flyweight Pattern in Go
🔍 Problem
You have a suddenly popular game server that's running on cheap cloud hosting and need to keep your memory usage down. Your biggest memory waster is your bullet system. Creating a new bullet object and storing it in ram every time a player fires is melting your server!
💭 Thoughts
This problem can be solved by reusing bullets, and a great way to do this is with a flyweight pattern in a simple pool structure.
The flyweight pattern is rarely seen in codebases these days. With memory being cheap, most programmers rarely need to consider how much they're using. So what is the flyweight pattern?
Flyweight is a structural design pattern that allows more objects to fit into the available amount of memory by sharing common parts of state between them. Instead of keeping all of the data in each object.
Despite its use being uncommon, there are some really good use cases for flyweight pattern in web services, a regular place you may find a flyweight pattern being used is connection pools, which can benefit from shared memory.
When to Use:
When your objects have some intrinsic properties which can be shared.
Use flyweight when a large number of objects needs to be created which can cause memory issues.
💡 Approach
Let's create our bullet struct, for storing bullet properties:
//Bullet match that gun with the right bullet
type Bullet struct {
    Energy   float64 // Energy in joules
    Velocity float64 // Bullet velocity in m/s
    Weight   int     // Weight in bullet grain
    Price    int     // Price in US cents
    Calibre  string  // Bullet calibre
}

Cool! So how do we create bullets? Let's make a function to generate a new bullet. Making sure we pick the correct bullet calibre.
//NewBullet - create a new bullet instance
func NewBullet(calibre string) *Bullet {
    switch calibre {
    case ".22LR ":
        return &Bullet{
            Calibre:  calibre,
            Velocity: 533,
            Energy:   150,
            Price:    7,
            Weight:   40,
        }
    case ".30 Carbine":
        return &Bullet{
            Calibre:  calibre,
            Velocity: 610,
            Energy:   1300,
            Price:    40,
            Weight:   110}
    case ".25 ACP":
        return &Bullet{
            Calibre:  calibre,
            Velocity: 340,
            Energy:   127,
            Price:    7,
            Weight:   35}
    case ".300 BLK":
        return &Bullet{
            Calibre:  calibre,
            Velocity: 675,
            Energy:   1840,
            Price:    70,
            Weight:   125}
    case "9mm":
        fallthrough
    default:
        return &Bullet{
            Calibre:  calibre,
            Velocity: 390,
            Energy:   570,
            Price:    7,
            Weight:   124}
    }
}

You'll notice we use a fallthrough to 9mm, just incase someone asks for a calibre we don't have. Hey, at least they'll have a bullet. We can't guarantee they'll actually be able to fire it. That's a problem for the frontend!
Now that we have our bullet generator, we need to make sure new bullets aren't needlessly created. So let's make a factory that checks the pool:

//BulletFactory - get an instance from the initialised pool
func BulletFactory(calibre string) *Bullet {
    if poolBullet, ok := pool[calibre]; ok {
        return poolBullet
    }

    bullet := NewBullet(calibre)
    pool[calibre] = bullet

    return bullet
}

This will check the pool for a bullet, and then provide that instead of creating a whole new bullet.
There you have it, a simple flyweight pattern using a pool.
⚠️Caveats
There's a couple of problems that I haven't addressed in this example:
What if the bullet is currently being used? Then we should create a new bullet and track usage.
This example is not threadsafe. We'll cover making maps threadsafe in a new NPAKB soon.
We're creating complexity. Is this actually needed? Maybe the server shouldn't track bullets as closely? Perhaps a refactor is required.
Optimisations are fun, but be aware of premature optimisations. It's also true that sometimes, the most commercial solution is just to pay for more server resources. As always, your mileage may vary.
“Premature optimisation is the root of all evil.”
Donald Ervin Knuth















Create a promotional discount bar in React and TypeScript
🔍 Problem
You want to give your members a 25% discount on your product for taking the time to sign up.
💡 Approach
For styling we're going to use Styletron, which is a CSS in JS library. Although backporting this to standard css would be trivial.
First we need to create our new project.
command line
cd ~/Projects
npx create-react-app discount-bar --typescript
cd discount-bar
# Adds the type definitions
npm install --save typescript @types/node @types/react @types/react-dom styletron-react @types/styletron-react

Start the dev server!
command line
npm run start

Add Styletron Provider to your index.tsx
./index.tsx
import { Provider as StyletronProvider } from "styletron-react"
import { Client as Styletron } from "styletron-engine-atomic"

const engine = new Styletron()

ReactDOM.render(
    <React.StrictMode>
        <StyletronProvider value={engine}>
            <App />
        </StyletronProvider>
    </React.StrictMode>,
    document.getElementById("root")
)

command line
touch PromoBar.tsx

Let's create our promoBar.tsx and get our discount bar started.
./promoBar.tsx
import * as React from "react"
import { useStyletron } from "styletron-react";

Let's get a basic top bar going.
const PromoBar = ({message, to, code}: Props) => {
        const [css] = useStyletron()
        const barStyle = css({
                display: "flex",
                justifyContent: "space-evenly",
                alignItems: "center",
                backgroundColor: "rgb(229, 28, 64)",
                color: "rgb(255,255,255)",
                position: "fixed",
                zIndex: 100,
                top: 0,
                left: 0,
                width: "100vw",
                height: "80px",
        })
}

export default PromoBar

For the layout of the insides of our promobar we're using Flex, justifyContent: space-evenly will ensure our items are spaced apart evenly, and alignItems; center will make them nice and centred.
Let's add some props, and render our bar!
interface Props {
        message: string //message to display to our users
        to: number //time to countdown to, in unix time
        code: string //the discount code
}

const PromoBar = ({ message, to, code }: Props) => {
    const [css] = useStyletron()
    const barStyle = css({
        display: "flex",
        justifyContent: "space-evenly",
        alignItems: "center",
        backgroundColor: "rgb(229, 28, 64)",
        color: "rgb(255,255,255)",
        position: "fixed",
        zIndex: 100,
        top: 0,
        left: 0,
        width: "100vw",
        height: "80px"
    })

    const countdownNumberStyle = css({
      display: "inline-block",
        background: "rgba(255,255,255,0.3)",
        borderRadius: "6px",
        padding: "5px",
        margin: "5px",
        minWidth: "30px",
        textAlign: "center",
  })

    return (
        <div className={barStyle}>
            <h2>{message}</h2>
            <h2>code: {code}</h2>
            <h2>
                <span
                    className={css({
                        marginRight: "4px"
                    })}>
                    Expires:
                </span>
                <div className={countdownNumberStyle}>0</div>
                <span>days</span>
                <div className={countdownNumberStyle}>0</div>
                <span>{":"}</span>
                <div className={countdownNumberStyle}>0</div>
                <span>{":"}</span>
                <div className={countdownNumberStyle}>0</div>
            </h2>
        </div>
    )
}

We'll now place it in our app render
import PromoBar from "./PromoBar"

const future = new Date()
future.setDate(future.getDate() + 2)

function App() {
    return (
        <div className="App">
            <header className="App-header">
                <img src={logo} className="App-logo" alt="logo" />
                <p>
                    Edit <code>src/App.tsx</code> and save to reload.
                </p>
                <a className="App-link" href="https://reactjs.org" target="_blank" rel="noopener noreferrer">
                    Learn React
                </a>
            </header>
            <PromoBar code={"DISCOUNTCODE"} to={future.getTime()} message={"25% off for members!"} />
        </div>
    )
}

Nice! However, wouldn't it be awesome if it was animated?
Let's add some animation to that Styletron style declaration.
    const discountBar = css({
        display: "flex",
        justifyContent: "space-evenly",
        alignItems: "center",
        backgroundColor: IntensiveColor,
        position: "fixed",
        zIndex: 999999,
        top: 0,
        left: 0,
        width: "100vw",
        height: "82px",
        animationDuration: "700ms",
        animationIterationCount: 1,
        animationFillMode: "forwards",
        animationName: {
            from: {
                top: "-82px",
            },
            to: {
                top: 0,
            },
        },
        [`@media only screen and (max-width: 950px)`]: {
            flexDirection: "row",
        },
        [`@media only screen and (max-width: 850px)`]: {
            flexDirection: "column",
            height: "120px",
            justifyContent: "center",
        },
    })

Hmm, we have some TypeScript errors now. animationName is does not match the typescript definitions, even though it is correct. No bother. We'll lodge a GitHub ticket and for now, fix it with an as any
            flexDirection: "column",
            height: "120px",
            justifyContent: "center",
        },
    } as any)

Alright! Looks great! But we're losing the top 80px of our app. Woops. Let's add some standard css and give our body some padding. With a nice animation too.
App.css
@keyframes slideDown {
    from {
        padding-top: 0;

    }
    to {
        padding-top: 80px;
    }
}

body.promo-bar {
    padding-top: 0;
    animation-duration: 700ms;
    animation-iteration-count: 1;
    animation-name: slideDown;
    animation-fill-mode: forwards;
    animation-delay: 100ms;
}

I've given the animation a delay of 100ms, so we don't see any tears between the two animations.
We'll then use a React hook to add the promo-bar class to the body.
./promoBar.tsx
import { useEffect } from "react";

    useEffect(() => {
        document.body.classList.add("promo-bar")
    }, [])

Beautiful.
But it doesn't countdown. That's a problem. Let's write a function to calculate the difference between now and when our promo code expires.
./promoBar.tsx

interface CountDownInfo {
    days: string
    hours: string
    minutes: string
    seconds: string
}

const updateCountdown = (countdownDate: number, setCountdown: (info: CountDownInfo) => void) => {
    // Get the current time and convert it to unix time
    const currentTime = new Date().getTime()

    // Get the time remaining until the countdown date
    const distanceToDate = countdownDate - currentTime

    // Calculate days, hours, minutes and seconds remaining
    const days = Math.floor(distanceToDate / (1000 * 60 * 60 * 24))
    const hours = Math.floor((distanceToDate % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60))
    const minutes = Math.floor((distanceToDate % (1000 * 60 * 60)) / (1000 * 60))
    const seconds = Math.floor((distanceToDate % (1000 * 60)) / 1000)
    // For aesthetics, lets give single digits a leading zero and set our countdown information
    setCountdown({
        days: `${days}`,
        hours: hours.toString().length === 1 ? `0${hours}` : `${hours}`,
        minutes: minutes.toString().length === 1 ? `0${minutes}` : `${minutes}`,
        seconds: seconds.toString().length === 1 ? `0${seconds}` : `${seconds}`,
    })
}

And create a setInterval in our promobar component, to update the timer every second. We'll add this to our on render hook. We'll also need a state hook to save the countdown information.
./promoBar.tsx
import { useEffect, useState } from "react";

    const [countdownInfo, setCountdownInfo] = useState<CountDownInfo>({
        days: "0",
        hours: "0",
        minutes: "0",
      seconds: "0",
  })
    useEffect(() => {
        document.body.classList.add("promo-bar")
        setInterval(() => updateCountdown(to, setCountdownInfo), 1000)
    }, [])

We should also clear the interval when the component is unmounted.
./promoBar.tsx
    useEffect(() => {
        document.body.classList.add("promo-bar")
        const interval = setInterval(() => updateCountdown(to, setCountdownInfo), 1000)
        return () => {
          //everything in this function will run when the component is unmounted
            clearInterval(interval)
            //let's remove the promo-bar class from the body for good measure
            document.body.classList.remove("promo-bar")
        }
    }, [])

Let's put the information into our bar.
./promoBar.tsx

    return (
        <div className={barStyle}>
            <h2>{message}</h2>
            <h2>code: {code}</h2>
            <h2>
                <span
                    className={css({
                        marginRight: "4px"
                    })}>
                    Expires:
                </span>
                <div className={countdownNumberStyle}>{countdownInfo.days}</div>
                <span>days</span>
                <div className={countdownNumberStyle}>{countdownInfo.hours}</div>
                <span>{":"}</span>
                <div className={countdownNumberStyle}>{countdownInfo.minutes}</div>
                <span>{":"}</span>
                <div className={countdownNumberStyle}>{countdownInfo.seconds}</div>
            </h2>
        </div>
    )

And to finish it off, let's add a hand copy into clipboard, so that our members won't have any difficulty putting their promo code into the cart.
We'll stick a copy emoji right next to the code so that they know what to do.
command line
npm install copy-to-clipboard --save

./promoBar.tsx
import copy from "copy-to-clipboard"

            <h2
                onClick={() => {
                    copy(code)
                }}>
                code: {code}
            </h2>

Which copies nicely, but the user doesn't realise! Let's add a state hook so that we can tell them the good news.
./promoBar.tsx
        const [copied, setCopied] = useState<boolean>(false)

        const copiedMsgStyle = css({
                fontSize: "0.4rem",
                marginLeft: "4px",
                opacity: 0.7
        })

        const pointer = css({
        cursor: "pointer"
    })



            <h2
              className={pointer}
                onClick={() => {
                        copy(code)
                        setCopied(true)
                }}>
                code: {code} 📋
                {copied && <small className={copiedMsgStyle}>copied</small>}
            </h2>

Annoyingly, the "copied" stays for ever. Let's add a setTimeout in a hook to take care of that.
./promoBar.tsx
    const pointer = css({
      cursor: "pointer"
  })
    useEffect(() => {
        if (copied) {
            setTimeout(() => {
                setCopied(false)
            }, 1000)
        }
    }, [copied])


And there you have it! A full working promotional bar with coupon code!
Check out the full example on GitHub
⚠️Caveats
We've not done anything to handle responsiveness. This will likely only look good on a desktop.
You'll have to figure out the coupon code generation yourself.
It could definitely look nicer.







Create middleware for HTTP handlers
🔍 Problem
You are constantly cut and pasting the same code for every handler that could be done in one go.
💡 Approach
Use middleware handlers to execute before the main one. In this example we'll edit the handlers to return an error, so you can handle errors in one spot.
package main

func main() {
    r := chi.NewRouter()
    r.Get("/", ExampleHandler)
}


func ExampleHandler(w http.ResponseWriter, r *http.Request) {
    // Handle the function
    // It is stateless with no additional parameters
}

Create the middleware that accepts a handler with a returned error, handle the error then return the handler that matches the http.HandlerFunc signature.
// WithError is middleware to check for errors
func WithError(handler func(w http.ResponseWriter, r *http.Request) (int, error)) http.HandlerFunc {
    fn := func(w http.ResponseWriter, r *http.Request) {
        code, err := handler(w, r)
        if err != nil {
            http.Error(w, code)
            return
        }
    }
    return fn
}

Update ExampleHandler to return an error and status code
func ExampleHandler(w http.ResponseWriter, r *http.Request) (int, error) {
    // Handle the function
    // It is stateless with no additional parameters
    // on error: return http.StatusBadRequest, err
    // on success: return http.StatusOK, nil
}

Plumb it up!
package main

func main() {
    r := chi.NewRouter()
    r.Get("/", WithError(ExampleHandler))
}

// WithError is middleware to check for errors
func WithError(handler func(w http.ResponseWriter, r *http.Request) (int, error)) http.HandlerFunc {
    fn := func(w http.ResponseWriter, r *http.Request) {
        code, err := handler(w, r)
        if err != nil {
            http.Error(w, err, code)
            return
        }
    }
    return fn
}

func ExampleHandler(w http.ResponseWriter, r *http.Request) (int, error) {
    // Handle the function
    // It is stateless with no additional parameters
    // on error: return http.StatusBadRequest, err
    // on success: return http.StatusOK, nil
}




Use functional handlers to add parameters to your handlers
🔍 Problem
You need to inject config to use in a HTTP handler.
💡 Approach
Use functional handlers. These are functions that return a http.HandlerFunc.
Instead of
func ExampleHandler(w http.ResponseWriter, r *http.Request) {
    // Handle the function
    // It is stateless with no additional parameters
}

func ExampleHandler(config *Config) func(w http.ResponseWriter, r *http.Request) {
    fn := func(w http.ResponseWriter, r *http.Request) {
        // Handle the function
        // You now have access to the config struct
    }
    return fn
}

Now when you declare your routes, you can inject config data:
func main() {
    config := NewConfig()
    r := chi.NewRouter()
    r.Get("/", ExampleHandler(config))
}

Use WaitGroups to sync up parallel tasks
🔍 Problem
You need to do two things at once, and need to wait for both to finish before continuing on.
💡 Approach
We can use wait groups for this problem. Channel are also a possibility.
func createSession(w http.ResponseWriter, r *http.Request) {
    fn := func(w http.ResponseWriter, r *http.Request) (int, error, string) {
    wg := &sync.WaitGroup{}
    wg.Add(1)
    go func(wg *sync.WaitGroup) {
        defer wg.Done()
        err := doSomething()
        if err != nil {
            fmt.Println(err)
        }
    }(wg)
    
    // Do other stuff
    wg.Wait()
}



