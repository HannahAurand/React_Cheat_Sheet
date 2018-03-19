#Componenet Life Cycle

##What is component life cycle? 

The circle of life in React revolves around components. They are the animals that rise and fall in their due time--some a mere blip on the screen of activity, but leave a life-time of impact, while others live long, tiring lives, accessed over and over again by an onslaught of relentless users. 

These creatures serve different purposes at different times in the React kingdom. Here they are, in the order they are accessed by the browser: 

####Mounting

Just like in nature, animals must mount one another to start life, certain methods are called at the start of the browser loading the page. The following methods are called when an instance of a component is being created and inserted into the DOM.

1. Initialization(): 
..."Hey honeybunny, can I come over?"
...This is where the DOM and React make first contact. React offers a virtual DOM.

2. ComponentWillMount():
...*Qeue Marvin Gay's sax intro "...Let's get it on"*
...componentWillMount() is invoked just before mounting occurs. It is called before render(), therefore calling setState() synchronously in this method will not trigger an extra rendering. Generally, we recommend using the constructor() instead.

3. Render(): 
...I've got no comparison for this one.

4. ComponentDidMount():
..."That was fun"
...componentDidMount() is invoked immediately after a component is mounted. Initialization that requires DOM nodes should go here. If you need to load data from a remote endpoint, this is a good place to instantiate the network request. This is where you can call API data. 
####Updating

5. componentWillReceiveProps()
6. shouldComponentUpdate()
7. componentWillUpdate()
8. componentDidUpdate


####Unmounting

9. componentWillUnmount
