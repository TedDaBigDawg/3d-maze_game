# 3d-maze_game
A 3d maze game made using ray casting and sdl2.

# 3D Maze
### Creating a 3D maze with raycasting
[Here](https://romhas.wixsite.com/3dmaze) you can go to the deployed site           
[Here](https://medium.com/@romhas/learning-game-development-through-a-maze-game-e0e5d84bb123) you can find a blog I made                
[Here](https://www.linkedin.com/in/romha-shwangzaw/) you can find my Linkedin profile

![textured_1](https://github.com/RomhaShwangzaw/Maze-Game/blob/main/screenshots/textured_1.png)
-----

### Table of Content
* [Purpose](#purpose)
* [Inspiration](#inspiration)
* [Data Flow](#data-flow)
* [Environment](#environment)
* [Installation](#installation)
* [Usage](#usage)
* [To-Do](#to-do)
* [Challenges](#challenges)
* [Contributing](#contributing)
* [Related Projects](#related-projects)
* [Resources](#resources)
* [Authors](#authors)
* [License](#license)
-----

### Purpose
For this project, I worked on developing a maze game from SDL2 (Simple DirectMedia Layer) in C language using a technique called Ray casting. Now you might think that this type of project doesn’t really represent something modern (for example). But the purpose of the project was to have a game so that people would have a little educational and challenging time. This project was created for all game lovers, young to old, all around the globe. My personal focus was to create a simple, engaging video game that anyone would love to play, and challenge my skills as a software engineer. Hence, with the project, I can teach in a fun way what ray casting is, how it works, and how it was such a breakthrough for the gaming industry.

-----

### Inspiration
I have been involved in the IT industry for more than 11 years, but I have never worked on a project involving video games. It is surprising considering the fact that I spent most of my childhood playing video games with friends and family. My friends and I used to spend most weekends playing Mario, Fifa, and car racing games until our fingers got sore. Growing up playing video games highly influences the way we see them and understand them, but I never stopped and considered the advances that they have made. When I learned that a technique such as ray casting presented a pseudo 3D game (Wolfenstein 3D), I knew that this was the right way to go. I am not personally looking to focus my career in game development but I always like to learn a bit from each specialization with the purpose of applying what is learned. Hence, it was a no brainer for me to go for this idea. By making my own version of a maze game, I got to learn and tried to develop it as something of a game that can be both challenging and educational.

-----
### Data Flow
![maze_architecture](https://miro.medium.com/v2/resize:fit:720/format:webp/1*5IExnwq2013nxkPCTx8_Og.png)
-----

### Environment
This game uses Simple DirectMedia Layer (SDL2) and Raycasting
- [SDL2](https://www.libsdl.org/download-2.0.php) and [SDL2_image](https://www.libsdl.org/projects/SDL_image/) are required to compile and use this program
-----

### Installation
- Clone this repository: `git clone "https://github.com/RomhaShwangzaw/Maze-Game"`
- Access The Maze directory: `cd Maze-Game`
- Compile the files with: `make all`
- Run the maze: `./maze` or `./maze maps/<map_name>`
- Disable textures: `./maze no_tex` or `./maze maps/<map_name> no_tex`

-----

### Usage
This 3D maze uses raycasting to draw the maze walls, utilizing [LodeV's](http://lodev.org/cgtutor/raycasting.html) method of using vectors to calculate ray length. By default the maze uses textures but textures can be disabled on execution.

#### Controls
- `W` or `↑` : move forward
- `S` or `↓` : move backward
- `A` or `←` : rotate camera left
- `D` or `→` : rotate camera right
- `Q` : strafe left
- `E` : strafe right
- `F` : toggle fullscreen
- `ESC` : quit

![textured_3](https://github.com/RomhaShwangzaw/Maze-Game/blob/main/screenshots/textured_3.png)

#### Maps
The maps are defined in 2D arrays in text files, which are parsed when passed as an argument to the maze executable. `0` represents open space, all other integers are drawn as walls.

Example:
```
1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
1 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 1
1 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 1
1 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 1
1 0 0 0 0 0 2 2 2 2 2 0 0 0 0 3 0 3 0 3 0 0 0 1
1 0 0 0 0 0 2 0 0 0 2 0 0 0 0 0 0 0 0 0 0 0 0 1
1 0 0 0 0 0 2 0 0 0 2 0 0 0 0 3 0 0 0 3 0 0 0 1
1 0 0 0 0 0 2 0 0 0 2 0 0 0 0 0 0 0 0 0 0 0 0 1
1 0 0 0 0 0 2 2 0 2 2 0 0 0 0 3 0 3 0 3 0 0 0 1
1 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 1
1 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 1
1 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 1
1 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 1
1 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 1
1 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 1
1 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 1
1 4 4 4 4 4 4 4 4 0 0 0 0 0 0 0 0 0 0 0 0 0 0 1
1 4 0 4 0 0 0 0 4 0 0 0 0 0 0 0 0 0 0 0 0 0 0 1
1 4 0 0 0 0 5 0 4 0 0 0 0 0 0 0 0 0 0 0 0 0 0 1
1 4 0 4 0 0 0 0 4 0 0 0 0 0 0 0 0 0 0 0 0 0 0 1
1 4 0 4 4 4 4 4 4 0 0 0 0 0 0 0 0 0 0 0 0 0 0 1
1 4 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 1
1 4 4 4 4 4 4 4 4 0 0 0 0 0 0 0 0 0 0 0 0 0 0 1
1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1 1
```

### To-Do
- Improved map parser
- Better error handling
- More textures
- Enemies / obstacles / objects
- Maze goal that loads next map
- Rain

### Challenges
The most challenging technical issue was something I had not foreseen at all. To my utter surprise, the trickiest part of the whole project was the concept behind ray casting, a technique used in this project to render the maze’s image onto the window. The concept of ray casting involves many high school math geometry principles, which have completely evaporated from my head. As a result of this new finding, I had to alter my plan and spent most of my time reading up on these trigonometric concepts. This left me with less time to build the actual project. However, my understanding of the concepts behind ray casting helped make coding a bit faster, not barring the fact that I had to take time away from my sleep.

### Contributing
For submitting patches and additions, please follow the "fork-and-pull" Git workflow.

 1. **Fork** the repo on GitHub
 2. **Clone** the project to your own machine
 3. **Commit** changes to your own branch
 4. **Push** your work back up to your fork
 5. Submit a **Pull request** so that I can review your changes

NOTE: Be sure to merge the latest from "upstream" before making a pull request!

-----

### Related Projects
This project is similar to Wolfenstein and Doom

![](https://www.sapphirenation.net/-/media/sites/sapphirenation/articles/2017/09/Wolf-3d-gameplay.jpg)
![](https://cdn.cloudflare.steamstatic.com/steam/apps/2280/ss_04a2879c2d052e9fb4a50380ddb00f660cc19dc3.600x338.jpg?t=1600098964)
-----

### Resources
- [SDL2 API](https://wiki.libsdl.org/CategoryAPI)
- [LazyFoo Beginning Game Programming](http://lazyfoo.net/tutorials/SDL/index.php)
- [Ray-Casting Tutorial For Game Development And Other Purposes by F. Permadi](http://permadi.com/1996/05/ray-casting-tutorial-table-of-contents/)
- [LodeV Raycasting Tutorial](http://lodev.org/cgtutor/raycasting.html)
- [Game Engine Black Book](https://www.amazon.com/Game-Engine-Black-Book-Wolfenstein/dp/1539692876)
-----

### Authors
Romha Shwangzaw Keneni - [Github](https://github.com/RomhaShwangzaw)

### License
Public Domain. No copy write protection.
