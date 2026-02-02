To start displaying a window. We should start making a Simple AEWindow, This will be the Window that the app will display.

```java
package astronomicengine.AEWindowTest;

import java.awt.Color;
import java.awt.Dimension;
import java.awt.Graphics2D;
import java.awt.image.BufferedImage;
import java.nio.Buffer;

import org.lwjgl.glfw.GLFW;

import astronomicengine.window.AEWindow;

public class MyWindow extends AEWindow {


    public MyWindow() {
        super(new Dimension(800, 600), "My Custom Window");

        setBounds(0, 800, 0, 600, -1, 1); // size

		System.out.println("The window is initialized");
    }

    @Override
    public void loop(double fps) {
        super.loop(fps);
        
		System.out.println("This is coming from the loop");
    }

    public static void main(String[] arg) throws Exception {
        if (!GLFW.glfwInit())
            throw new Exception();

        MyWindow window = new MyWindow();
        window.startDisplaying();
    }
}
```
