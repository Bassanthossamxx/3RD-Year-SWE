

# OpenGL Basics Guide


## 1. Writing OpenGL Code for the First Time

To start with OpenGL, you need a basic setup. Here’s a template to initialize an OpenGL window and render content:

```cpp
#include <GL/glut.h>

void display() {
    // Add drawing code here
    glFlush();
}

int main(int argc, char** argv) {
    glutInit(&argc, argv);                // Initialize GLUT
    glutInitDisplayMode(GLUT_SINGLE | GLUT_RGB); // Set display mode
    glutInitWindowPosition(100, 100);      // Set window position
    glutInitWindowSize(600, 600);          // Set window size
    glutCreateWindow("OpenGL Window");     // Create window with title
    gluOrtho2D(0, 200, 0, 200);            // Set 2D orthographic projection

    glutDisplayFunc(display);              // Register display callback function
    glutMainLoop();                        // Enter the event-processing loop

    return 0;
}
```

This code sets up a basic OpenGL window where you can start rendering shapes.

---

## 2. Changing the Background Color

To change the background color, use `glClearColor`. The format for this function is:

```cpp
glClearColor(red, green, blue, alpha);
```

Each color component (red, green, blue) should be a value between 0.0 and 1.0. The alpha value controls transparency but is usually set to `1.0` for opaque backgrounds.

#### Example Background Colors
- **Black**: `glClearColor(0, 0, 0, 1);`
- **White**: `glClearColor(1, 1, 1, 1);`
- **Red**: `glClearColor(1, 0, 0, 1);`
- **Green**: `glClearColor(0, 1, 0, 1);`
- **Blue**: `glClearColor(0, 0, 1, 1);`
- **Gray**: `glClearColor(0.5, 0.5, 0.5, 1);`
- **Transparent Black**: `glClearColor(0, 0, 0, 0);` (useful for blending effects)

---

## 3. Changing the Color of Points

To set the color of a point, use `glColor3f`:

```cpp
glColor3f(red, green, blue);
```

Each color component should be between `0.0` and `1.0`.

#### Example Point Colors
- **Red**: `glColor3f(1, 0, 0);` (bright red)
- **Green**: `glColor3f(0, 1, 0);` (bright green)
- **Blue**: `glColor3f(0, 0, 1);` (bright blue)
- **White**: `glColor3f(1, 1, 1);`
- **Black**: `glColor3f(0, 0, 0);`
- **Yellow**: `glColor3f(1, 1, 0);`
- **Cyan**: `glColor3f(0, 1, 1);`
- **Magenta**: `glColor3f(1, 0, 1);`
- **Gray**: `glColor3f(0.5, 0.5, 0.5);`

---

## 4. Drawing Points with Different Data Types

To draw points, you can use `glBegin(GL_POINTS)` with different functions to specify the point coordinates based on data type:

### Functions and When to Use Them
- **`glVertex2i(x, y)`**: Accepts two integers. Use this when you have whole-number coordinates and want to avoid floating-point calculations for simplicity.
- **`glVertex2f(x, y)`**: Accepts two floats. Use this for fractional coordinates when you need more precise control over positioning, as with smooth movements or animations.
- **`glVertex2d(x, y)`**: Accepts two doubles. Use this when extremely high precision is needed for point positioning, such as in scientific simulations or detailed graphics.

### Example of Drawing Points with Different Functions

```cpp
glPointSize(10);        // Set the point size

// Integer coordinates
glBegin(GL_POINTS);
glVertex2i(50, 50);     // Position the point at (50, 50) using integers
glEnd();

// Float coordinates
glBegin(GL_POINTS);
glVertex2f(75.5f, 75.5f); // Position the point at (75.5, 75.5) using floats
glEnd();

// Double coordinates
glBegin(GL_POINTS);
glVertex2d(100.0, 100.0); // Position the point at (100, 100) using doubles
glEnd();
```

---

## 5. OpenGL Point Functions with Arrays and Classes

OpenGL provides flexibility in how you define and reference points, allowing you to use arrays or classes to organize point data.

### 5.1 Using Arrays for Point Coordinates

Using arrays is an efficient way to store multiple points' coordinates, which can then be referenced in OpenGL drawing functions.

#### Example:
```cpp
int point1[] = {50, 100};    // Define a point at (50, 100)
int point2[] = {75, 150};    // Define a point at (75, 150)
int point3[] = {100, 200};   // Define a point at (100, 200)

glBegin(GL_POINTS);           // Start specifying points
glVertex2iv(point1);          // Draw the first point using integer array
glVertex2iv(point2);          // Draw the second point
glVertex2iv(point3);          // Draw the third point
glEnd();
```

**Explanation**:
- **`int point1[]`**: Declares an integer array representing coordinates for a point.
- **`glVertex2iv(point1)`**: The function `glVertex2iv` takes a pointer to an integer array with two elements for the x and y coordinates, allowing you to use integer arrays for positioning.

---

### 5.2 Using a Class to Define Points

Alternatively, you can create a class to represent a point in 2D space, making your code more modular, especially useful when working with numerous points.

#### Example:
```cpp
class wcPt2D {
public:
    GLfloat x, y;             // Coordinates for the point
};

wcPt2D pointPos;               // Declare an object of wcPt2D
pointPos.x = 45.3f;            // Set x-coordinate
pointPos.y = 120.75f;          // Set y-coordinate

glBegin(GL_POINTS);            // Start specifying points
glVertex2f(pointPos.x, pointPos.y); // Draw the point at (45.3, 120.75)
glEnd();
```

**Explanation**:
- **`class wcPt2D`**: Defines a class with `GLfloat` (floating-point) values `x` and `y`.
- **`wcPt2D pointPos;`**: Creates an object of `wcPt2D`, allowing you to set specific x and y values for a point.
- **`glVertex2f(pointPos.x, pointPos.y);`**: Uses the values stored in `pointPos` to specify the point’s position. 

## 6. Complete Example with Points in Different Colors and Data Types

Here's a complete example that sets a background color, changes point colors, and draws three points using various data types for coordinates.

```cpp
#include <GL/glut.h>

void display() {
    glClearColor(1, 1, 1, 1);       // White background
    glClear(GL_COLOR_BUFFER_BIT);    // Clear the color buffer

    // First Point: Red (using integer coordinates)
    glColor3f(1, 0, 0);              // Set color to red
    glPointSize(10);                 // Set point size
    glBegin(GL_POINTS);
    glVertex2i(50, 50);              // Draw point at (50, 50)
    glEnd();

    // Second Point: Blue (using float coordinates)
    glColor3f(0, 0, 1);              // Set color to blue
    glPointSize(10);                 // Set point size
    glBegin(GL_POINTS);
    glVertex2f(100.5f, 100.5f);      // Draw point at (100.5, 100.5)
    glEnd();

    // Third Point: Green (using double coordinates)
    glColor3f(0, 1, 0);              // Set color to green
    glPointSize(10);                 // Set point size
    glBegin(GL_POINTS);
    glVertex2d(150.0, 150.0);        // Draw point at (150.0, 150.0)
    glEnd();

    glFlush();                       // Render now
}

int main(int argc, char** argv) {
    glutInit(&argc, argv);                // Initialize GLUT
    glutInitDisplayMode(GLUT_SINGLE | GLUT_RGB); // Set display mode
    glutInitWindowPosition(100, 100);      // Set window position
    glutInitWindowSize(600, 600);          // Set window size
    glutCreateWindow("Colored Points with Different Coordinates"); // Create window with title
    gluOrtho2D(0, 200, 0, 200);            // Set 2D orthographic projection

    glutDisplayFunc(display);              // Register display callback function
    glutMainLoop();                        // Enter the event-processing loop

    return 0;
}
```

This example displays three points:
- A **red point** at position `(50, 50)` using integer coordinates
- A **blue point** at position `(100.5, 100.5)` using float coordinates
- A **green point** at position `(150.0, 150.0)` using double coordinates

Each point has a size of `10`, and the background is set to white.