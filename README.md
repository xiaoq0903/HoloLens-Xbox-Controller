# Hololens Xbox Controller Plugin

![holoens controller](https://user-images.githubusercontent.com/18353476/29101706-017fa182-7c69-11e7-9a7c-4aa6eaa3d432.jpg)

[Using an Xbox One Controller with Unity on Windows 10](https://ritchielozada.com/2016/01/16/part-11-using-an-xbox-one-controller-with-unity-on-windows-10/)

Instructions:

1)	Pair your Xbox One S Wireless Controller to your HoloLens using the Bluetooth section of HoloLens Settings and following the instructions of your controller.

2)	Make sure your Unity WSA project has the following capabilities set:

		InternetClient
		
		HumanInterfaceDevice
		
3)	Set up the script you are going to use for input as follows.  (You can follow the example of the scene “ExampleScene” and the script “ControllerInputExample” to see how to use the code)

	a.	Add the using directive “using HoloLensXboxController;”
	
	b.	Add a private member “private ControllerInput controllerInput;”
	
	c.	Instantiate the controllerInput object in the Start() method:  ie “controllerInput = new ControllerInput(0, 0.19f);”.  The first parameter of the constructor is the number, starting at zero, of the controller you want to follow.  The second parameter is the default “dead” value; meaning all stick readings less than this value will be set to 0.0.
	
	d.	Make sure to call “controllerInput.Update();” in your MonoBehaviour Update() method.
	
4)	Build and deploy your application to HoloLens.

5)	Note:  these libraries will only handle Input on the HoloLens.  They will not handle input in the Unity Editor.  You will need to handle that separately.
