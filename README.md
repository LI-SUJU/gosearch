# gosearch
## intro
This is a web application based on react framework: it provides search services of Google, Baidu and other websites, provides a music player based on Netease api, and provides two fun functions: "wonderful sentence" and "today in history". 
This project has been deployed on my personal website: http://www.gosearch.cn
## project directory ( branch: master )
- build: (after using the npm run build command) the package packaged by webpack (convert react jsx to js, remove code comments, etc.)
- node-modules: store all node modules used in this project. The node modules commonly used in the project are:
  - pubsub-js (provides communication between components)
  - react
  - axios (asynchronous style encapsulation of xhr that can be used to send http requests and get server response)
  - nanoid (generate a unique ID number)
  - react-router-dom (using route, redirect, navlink, HashRouter which is exposed by it)
- public: The core of public is the index.html file, and nodes on this page whose id is "root" will load the src/App.js rendered by src/index.js
- src
  - components
    - Battery: power display (this component is not introduced in the final project)
    - Clock: mounted on home page
    - Event: render the props from the parent component Todayonhistory. You can click to redirect to the corresponding Baidu encyclopedia page.
    - Input: input box component that sends searching terms to the specified api, stores the returned json data in State after processing, and broadcasts the song information (songid) (this component is introduced in src/pages/MusicSearch/MusicSearch.jsx)
    - Loading: the dynamic loading page displayed before the content of the home page is loaded, which is actually a div node with a large z-index value; this component slides out after the content of the web page is fully loaded
    - Logo: responsible for the logo display in the upper left corner of the home page
    - Music: responsible for the goMusic function in the upper right corner of the home page, and implements a music searching and playing component based on Netease api
    - Oneword: responsible for the "wonderful sentence" component at the bottom of the home page, which will be refreshed every 5 minute
    - Search: home page search component, which integrates quick jump to Baidu, Bilibili, CSDN, Zhihu and Google
    - Tab: provide quick access to Tencent's QQ Music, QQ Mail and Translator
    - Todayonhistory: displays the knowledge bar of "Today in History". Each historical event is rendered by the child component Event
  - font: holds the author's favorite font ( Zhankukuaileti ), but it is not put into use in the end
  - pages: route component, introduced in src/components/Music
    - Help: help component
    - Hot:  frequently search component
    - HotSearchDetail: child component of Hot
    - MusicSearch: music searching component
      - MusicSearchDetail: child component of MusicSearch
- .gitignore: configure git to ignore changes in node_modules
- package-lock.json/package.json: configuration file, you can view the version of the dependent module, package configuration, etc.
## acknowledgement
- Thanks to the NetEase music related service provided by this api: https://cloud-music-api-f494k233x-mgod-monkey.vercel.app/ (this api description document: https://neteasecloudmusicapi.vercel.app/)
- Thanks to the historical data service provided by this api: https://api.yum6.cn/briefing/baidu.php?format=json
- Thank you for your valuable advice and support.
## declaration of responsibility
- Developer do not bear any responsibility for disclosing api data, and the data content is maintained by public api.
- Do not commercialize the music files provided by this project, and the consequences will be borne by the users.
