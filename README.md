# Computer--Graphic-chess-board

#include <GL/glut.h>

void drawSquare(int x, int y)
{
    glBegin(GL_POLYGON);
    glVertex2f(x, y);
    glVertex2f(x + 1, y);
    glVertex2f(x + 1, y + 1);
    glVertex2f(x, y + 1);
    glEnd();
}

void display()
{
    int i, j;
    for (i = 0; i < 8; i++)
    {
        for (j = 0; j < 7; j++)
        {
            if ((i + j) % 2 == 0)
            {
                glColor3f(1.0, 1.0, 1.0);
            }
            else
            {
                glColor3f(0.0, 0.0, 0.0);
            }
            drawSquare(i, j);
        }
    }
    glFlush();
}

int main(int argc, char *argv[])
{
    glutInit(&argc, argv);
    glutCreateWindow("Chess Board");
    glutDisplayFunc(display);
    glutMainLoop();
    return 0;
}
