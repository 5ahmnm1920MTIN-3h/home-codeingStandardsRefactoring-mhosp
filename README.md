# home-codeingStandardsRefactoring-mhosp

# Ausarbeitung Refactoring

## Was ist Refactoring Definition in eigenen Worten?
Refactoring ist den Code ,durch Überarbeiten, leserlicher und übersichtlicher zu machen.

## Welche Vorteile/Nachteile birgt Refactoring?
 + Der Code ist für andere Personen besser leserlich, genauso wie für einen selbst, wenn man nach längerer Zeit 
 + Ein Nachteil ist der zeitliche Aufwand den Refactoring mit sich bringt

## Was sind die Refactoring-Schritte?
 + Testcase definieren.  
 + Schauen ob programm funktioniert.  
 + Code Smell beseitigen.  
 + Testcase ausprobieren ob alles noch funktioniert.  
 + Wenn ja, commiten.

## Prinzipien von gutem Code?
 + DRY -Don’t Repeat Yourself
 + KISS -Keep it Simple, Stupid
 + YAGNI -You Ain’t Gonna Need Principle of least Astonishment 
 + SoC-Separation of Concerns

## Was versteht man unter Code Smell?
Code der unnötig lange und umständlich geschrieben ist. Code Smells können oft fehleranfällig sein.

## Recherche von 10 Code Smells die euer Projekt betreffen können, inkl. Beschreibung und Beispiel.

#### 1. Magical String – String der mehr als einmal verwendet wird und immer wieder gehardcodet ist.
<code> 
  
    private void Movement () 
    {
    float axisV = Input.GetAxis("Horizontal");
    float axisH = Input.GetAxis("Vertical");
    }
</code>
  
#### 2. Methode zu lange – Methode die mehr als 25 Zeilen Code hat.
Player Controller Script: Der Rotation Code sollte vom Movement Code getrennt sein

#### 3. Magical Value – Ein Wert wie z.B.: float oder int der ohne Beschreibung und Kontext verwendet wird. 
<code>
  
     private void Movement ()
     {
      float axisV = Input.GetAxis("Horizontal") * 5f;
      float axisH = Input.GetAxis("Vertical") - 10f;
    }
  
</code>

#### 4. Klasse zu lange – Klasse die mehr als 400 Zeilen Code hat.
GameManager und MenuManager haben geteilt jeweils weniger als 400 Zeilen Code.

#### 5. Unnötig viele Methoden – Viele kleinere Methoden welche durch allgemeine ersetzt werden können. 
2 separate Methoden die einige Elemente deaktivieren und oder aktivieren können durch Angabe eines boolschen Parameter einheitlich gemacht werden.

<code>
  
    private void GenericSceneLoader (string sceneToLoad)
    {
      SceneManager.LoadScene(sceneToLoad);
    }
  
</code>

#### 6. Unnötige Namespace Angaben – Nicht verwendete Namespaces die trotzdem angegeben sind.
<code>
   
    using System.Collections;  
    using UnityEngine;
  
    pubic class Test : MonoBehaviour 
    {
      private void Update ()
      {
        Debug.Log("Not using System.Collections");
      }
    }
  
 </code> 

#### 7. Fehlende Angabe von Access Modifiern – private sollte immer angegeben werden auch wenn dies nicht vorgeschrieben ist damit es funktioniert.
<code>
  
    float number;
    private float number;
</code>

#### 8. Variablen Deklaration mitten im Code – Variablen die nicht ganz oben in der Klasse stehen
<code>
   
    using UnityEngine;
  
    pubic class Test : MonoBehaviour 
    {
      private float guteVariable;
    
      private void Update ()
      {
        Debug.Log("Made by Leonhard Schnaitl");
      }
      
      private static string wrongVarPlacement;
      
      public void SomeMethod ()
      {
        //Code
      }
    }
  
 </code> 

#### 9. Unnötige Leerzeilen – Sinnlos viele Leerzeilen zwischen Zeilen von Code.  
<code>
    
    private float number;
    
    
    
    
    
    private void GenericSceneLoader (string sceneToLoad)
    {
    
    
      SceneManager.LoadScene(sceneToLoad);
    }
  
</code>

#### 10. Falsche Klammer-Setzung – Die Klammern werden nicht einheitlich oder unklar gesetzt.
<code>
  
    if (true  
    )  
    {  
    //Code}
    
</code>

# Santa Run

### Project description: 
This is a simple 2D side-scroll game. The Santa runs from left to right and has to avoid some obstacles by jumping over them.
The game ends when the Santa hits an obstacle.  The goal is to avoid as many obstacles as possible.

### Development platform: 
Windows 10, Unity version 2019.1.14f1, Visual Studio Community 2017, Scripting Runtime Version: .NET 4.0

### Target platform: 
WebGl and Standalone, RefRes: 1920 * 1080


### Visuals: 
<div>
<img src = "./Screenshots/sketch-SantaRun.JPG" width = "500">
</div>

[![SANTA RUN](https://i9.ytimg.com/vi/2C74XxBkFfI/mq1.jpg?sqp=CNWnze8F&rs=AOn4CLBrmO-tJ3gQ2BNeMxvrmQcsIhhcgQ)](https://www.youtube.com/embed/2C74XxBkFfI "Santa RUN")

https://www.youtube.com/embed/2C74XxBkFfI

### Necessary setup/execution steps: 
For playing the game go to: 
* WebGL: https://hs-teaching.github.io/WegGL-SantaRun/
* Standalone (.exe): Clone project and publish as Standalone

For development: Clone this project. 

### Third party material: 
* This game is based on the game Santa Run developed by Raja Biswas in the Udemy-course Unity 2018 Game Developmen by Example 
[Unity 2018 Game Development by Example](https://www.udemy.com/course/unity-2d-game-development-by-example/).
* Sprites are used from https://www.gameart2d.com/santa-claus-free-sprites.html


### Project state: 
Program is working correctly, no errors, refactoring is needed.
Refactoring needed: 
* del not used namespaces
* del unused variables
* del needless debugs
* del needless comments
* del unused methods
* rename variables (coding standards)
* rename methods (coding standards)
* fix poor conditional clauses
* fix poor formating
* replace magic string
* replace magic number

### Limitations: 
Only one level is implemented. 

### Lessons Learned: 
* Create 2D Scenes
* Use Quads for moving Backgrounds (Textures instead of Sprites)
* Use Particle System for snowing effect.
* Use Scene Management for switching between Scenes
* Create and control Animations (Animation, Animator and Scripts)
* Use the singelton pattern
* Spawn objects
* Use UI elements and manipulate UI elements with scrips


Copyright by smeerws
