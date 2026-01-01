# midpoint-circle-algorithm-smily-face-

import pygame
import sys

# Initialize Pygame
pygame.init()

# Set up the display
WIDTH, HEIGHT = 800, 600
screen = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("circle") #set exe header

# Colors
WHITE = (255, 255, 255)
BLACK = (0, 0, 0)


# Function to draw a line using DDA algorithm
def circle(xc,yc,r):
    p0=1-r
    x0=0
    y0=r
    while(x0<=y0):
        if(p0<0):
            x0=x0+1
            y0=y0
            p0=p0+2*x0+1
        else:
            x0=x0+1
            y0=y0-1
            p0=p0+(2*x0)-(2*y0)+1
        screen.set_at((xc + x0, yc + y0), WHITE)
        screen.set_at((xc - x0, yc + y0), WHITE)
        screen.set_at((xc + x0, yc - y0), WHITE)
        screen.set_at((xc - x0, yc - y0), WHITE)
        screen.set_at((xc + y0, yc + x0), WHITE)
        screen.set_at((xc - y0, yc + x0), WHITE)
        screen.set_at((xc + y0, yc - x0), WHITE)
        screen.set_at((xc - y0, yc - x0), WHITE)
        
def semicircle(xc,yc,r):
    p0=1-r
    x0=0
    y0=r
    while(x0<=y0):
        if(p0<0):
            x0=x0+1
            y0=y0
            p0=p0+2*x0+1
        else:
            x0=x0+1
            y0=y0-1
            p0=p0+(2*x0)-(2*y0)+1
        screen.set_at((xc + x0, yc +y0), WHITE)
        screen.set_at((xc - x0, yc +y0), WHITE)
        
        

# Main loop
def main():
    while True:
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                pygame.quit()
                sys.exit()

        # Clear the screen
        screen.fill(BLACK)

        # Draw a line using DDA algorithm
        circle(400,200,120)
        circle(350,150,10)
        circle(450,150,10)
        circle(400,200,120)
        semicircle(400,200,60)
        
        
        
        # Update the display
        pygame.display.flip()


if __name__ == "__main__":
    main()
