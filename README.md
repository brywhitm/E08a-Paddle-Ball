# E08a-Godot
The first Godot exercise for BL-MSCH-C220. As usual, Fork and Clone this repository.

Here are instructions for your first experience with the Godot engine:

 * Open Godot. In the project viewer, select Import.
 * Click Browse, and find the folder that contains your Cloned Project. Select the project.godot file and Open it. Import & Edit.
 * Change the viewport (at the top of the editor window) to 2D
 * In the Viewport Toolbar, select View > Show Grid
 * In the Viewport Toolbar, select the three vertical dots. Make sure Snap to grid is checked
 * In the Viewport Toolbar, select the three vertical dots > Configure Snap
   * Change the Grid Step to 32 px by 32 px
 * In the Viewport Toolbar, press the icon that looks like three dots with a horseshoe. This will turn snapping on.
 * In the Scene panel, push the + icon and Create a Node
 * Double-click on the new Node, and rename it to World
 * Right-click on World and Add Child Node; search for Physics
 * Create a KinematicBody2D node and rename it to Paddle
 * Right-click on World and Add Child Node; search for Physics
 * Create a RigidBody2D node and rename it to Ball
 * Right-click on World and Add Child Node; search for Physics
 * Create a StaticBody2D node and rename it to Wall
 * Right-click on the Paddle node and Add Child Node; search for Sprite
 * Add a Sprite Node. Select it.
 * In the FileSystem panel, find Assets > paddle.png. Drag that image to the Inspector Panel > Sprite > Texture box
 * In the Scene Panel, select Paddle. In the Viewport Toolbar, push the icon that looks like two interlocking squares with white dots in the corners (“Makes sure the object’s children are not selectable”). You should see that same icon appear next to the Paddle in the Scene Panel.
 * Drag the Paddle to the center, near the bottom, of the viewport area
 * Right-click on the Ball node and Add Child Node; search for Sprite
 * Add a Sprite Node. Select it.
 * In the FileSystem panel, find Assets > ball.png. Drag that image to the Inspector Panel > Sprite > Texture box
 * In the Scene Panel, select Ball. Make it so that its children are not selectable (by pressing the icon in the Toolbar)
 * Drag the Ball above the Paddle
 * Right-click on the Wall Node and Add Child Node. Search for CollisionPolygon
 * Create a CollisionPolygon2D Node
 * With the CollisionPolygon2D node selected, draw a shape that covers the sides and top of the Viewport, extending slightly below the bottom. Leave the bottom of the viewport uncovered. Make the polygon two squares thick on all three sides. When you are done (returned to the original vertex), the polygon should fill with red, cyan, and purple
 * Right-click on the Paddle node; Add Child Node. Search for Collision
 * Add a CollisionShape2D node. In the Inspector Palette, select CollisionShape2D > Shape and change it to New RectangleShape2D
 * Select the CollisionShape2D node in the Scene Palette. Use the red circle handles to make the CollisionShape2D the same size as the sprite (you might need to turn off snapping to accomplish this)
 * Right-click on the Ball node; Add Child Node. Search for Collision
 * Add a CollisionShape2D node. In the Inspector Palette, change the shape to New CircleShape2D
 * Select the Ball’s CollisionShape2D. Use the handles to make the diameter of the CollisionShape2D the same as the sprite’s
 * You can now run the Scene. It will ask you to save the scene. Call it world.tscn, and save it in the Scenes folder
 * The ball should now fall and rest on the paddle
 * Let's update the attributes of the Ball. Select it in the Scene Palette
 * In the Inspector Palette:
   * Change the Mode to Character
   * Select the Physics Material > New PhysicsMaterial
   * Change the Gravity Scale to 0
   * Linear > Velocity
     * Change x to 200
     * Change y to -200
     * Change Damp to 0
   * Angular
     * Change Damp to 0
   * Physics Material > Edit
     * Change Friction to 0
     * Change Bounce to 1
 * Run the scene. If the editor asks you to select a main scene, select world.tscn
 * You should see the ball bounce off the walls and the paddle
 * We now need to make the paddle move
 * In the Scene Panel, right-click on the Paddle Node. Select Attach Script
 * Change the Path to res://Scripts/paddle.gd
 * Select Create
 * Delete lines 3–14
 * Starting on line 3, type:
    ```python
    func _physics_process(delta):
      var mouse_x = get_viewport().get_mouse_position().x
      position = Vector2(mouse_x, position.y)
    ```
 * Save the script and run the scene
 
 If you have a paddle that follows the mouse, and a ball that bounces off the walls and the mouse, you have completed the exercise. Save the Scene, commit it to Github, edit your LICENSE and README.md, and turn in the URL of your repository to Canvas.
