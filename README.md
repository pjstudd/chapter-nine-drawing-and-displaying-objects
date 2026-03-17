# Chapter 9: Drawing and Displaying Objects

## Overview

In game development, objects must be displayed on the screen so the
player can see and interact with them. In **Pygame**, objects such as
shapes, images, and text are drawn onto a special surface called the
**screen surface**.

This chapter introduces the basic methods used to **draw objects**,
**position them using coordinates**, and **update the screen** so the
changes appear during the game.

------------------------------------------------------------------------

# 9.1 Working with Surfaces and Coordinates

In Pygame, everything that appears on the screen is drawn on a
**Surface**.

A **Surface** is an area where images, shapes, and text are rendered.
The main surface is the **game window** created using:

``` python
screen = pygame.display.set_mode((800, 600))
```

This surface represents the **display window** where all game graphics
appear.

### Coordinate System

Pygame uses a **2D coordinate system** to position objects.

-   The **top-left corner** of the screen is `(0, 0)`
-   The **x-axis** moves **left to right**
-   The **y-axis** moves **top to bottom**

Example coordinates:

    (0,0) --------------------> x
      |
      |
      |
      v
      y

If we draw an object at `(100, 200)`, it means: - 100 pixels from the
left - 200 pixels down from the top

Understanding coordinates is important for placing and moving objects in
a game.

------------------------------------------------------------------------

# 9.2 Drawing Shapes, Text, and Images

Pygame allows developers to draw different objects on the screen.

### Drawing Shapes

Shapes such as rectangles and circles can be drawn using the
`pygame.draw` module.

Example:

``` python
pygame.draw.rect(screen, (255, 0, 0), (100, 150, 200, 100))
```

Explanation: - `screen` → surface where the shape is drawn - `(255,0,0)`
→ color (red) - `(100,150,200,100)` → position and size

This draws a **red rectangle** starting at `(100,150)` with width
**200** and height **100**.

------------------------------------------------------------------------

### Drawing Text

Text is created using the **Font module**.

Example:

``` python
font = pygame.font.SysFont(None, 36)
text = font.render("Hello Pygame", True, (0,0,0))
screen.blit(text, (50, 50))
```

Explanation: - A font is created. - The text is rendered into an
image. - The text image is placed on the screen using `blit()`.

------------------------------------------------------------------------

### Displaying Images

Images can also be displayed using `pygame.image.load()`.

Example:

``` python
image = pygame.image.load("cat.png")
screen.blit(image, (200, 200))
```

This loads an image and displays it at the given coordinates.

------------------------------------------------------------------------

# 9.3 Updating the Screen with `pygame.display.update()`

After drawing shapes, images, or text, the screen **will not change
automatically**.

We must update the display using:

``` python
pygame.display.update()
```

This command refreshes the window and shows the new graphics.

Without updating the display, the player will **not see any changes on
the screen**.

In most games, the display is updated **inside the game loop** so that
graphics continuously refresh.

------------------------------------------------------------------------

# 9.4 Understanding RGB Colors and Screen Refresh

Colors in Pygame use the **RGB color model**.

RGB stands for:

-   **R** -- Red
-   **G** -- Green
-   **B** -- Blue

Each color value ranges from **0 to 255**.

Examples:

  Color    RGB Value
  -------- ---------------
  Black    (0,0,0)
  White    (255,255,255)
  Red      (255,0,0)
  Green    (0,255,0)
  Blue     (0,0,255)
  Yellow   (255,255,0)

Example of filling the screen with a color:

``` python
screen.fill((135, 206, 235))
```

This fills the screen with a **sky blue color**.

------------------------------------------------------------------------

# Example Program: Drawing Objects on the Screen

The program below demonstrates how to draw **a rectangle, a circle, and
text** on the screen.

``` python
import pygame

pygame.init()

screen = pygame.display.set_mode((800, 600))
pygame.display.set_caption("Drawing Objects Example")

clock = pygame.time.Clock()

running = True

while running:

    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

    screen.fill((200, 220, 255))

    pygame.draw.rect(screen, (255, 0, 0), (100, 100, 200, 100))

    pygame.draw.circle(screen, (0, 255, 0), (400, 300), 50)

    font = pygame.font.SysFont(None, 36)
    text = font.render("Hello Pygame!", True, (0,0,0))
    screen.blit(text, (300, 50))

    pygame.display.update()

    clock.tick(60)

pygame.quit()
```

------------------------------------------------------------------------

# Summary

In this chapter, we learned how to:

-   Work with **Surfaces and coordinates**
-   Draw **shapes, text, and images**
-   Update the screen using **pygame.display.update()**
-   Use **RGB color values** to control screen colors

These concepts are essential for displaying objects and graphics in a
game.

# Coding Exercise 3: Drawing a Simple Scene in Pygame

## Objective
The objective of this activity is to practice drawing objects on the screen using Pygame. In this coding exercise, students will apply their knowledge of surfaces, coordinates, shapes, RGB colors, and screen updates to recreate a simple scene.

## Instructions

1. Observe the sample output image provided by the instructor (Please see the file codingExerciseThreeOutput.png).
2. Create a Pygame program that reproduces the same scene shown in the screenshot.
3. Your program must create a game window with a size of **800 × 600 pixels**.
4. Use RGB colors to create the background and the objects in the scene.
5. Draw the following objects using Pygame drawing functions:
   - A sky background
   - A green ground
   - A sun
   - A house
   - A door
   - A window

6. Use the coordinate system properly to position the objects so that they match the instructor's sample output.
7. Make sure the program updates the display so the shapes and objects appear in the game window.
8. The program should continue running until the user closes the window.

## Reminder

- Use proper RGB color values.
- Ensure that the objects appear in the correct positions.
- Your output should closely match the instructor's sample image.