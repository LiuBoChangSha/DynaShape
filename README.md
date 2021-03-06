﻿<img src="https://cdn-business.discourse.org/uploads/dynamobim/original/3X/8/c/8cb1f156ee18209847ec7807f4dfc5e2145ba45d.png" width = "900">

## Build, package and install

The source code is written entirely in Visual C#. The dependent dll files are as follow
- All core Dynamo dlls can be found in the main Dynamo Core main folder (e.g. *C:\Program Files\Dynamo\Dynamo Core\1.x*)
- *MathNet.Numerics.dll (which can be downloaded from NuGet, recommended version 3.11 or above). Normally this will be done automatically by Visual Studio NuGet Manager right at the first time you build the project on your computer.
- *MeshToolkit.dll*. This is contained within the MeshToolkit package, which can be downloaded with the Dynamo package manager. 

After *DynaShape.dll* has been built successfully from the source, you can then assemble the Dynamo package folder according to the following structure:

<pre>
_DynaShape
├── pkg.json (provided with the Visual Studio solution)
└── bin
    ├── DynaShape.dll
    ├── DynaShape_DynamoCustomization.xml (provided with the Visual Studio solution)
    └── MathNet.Numerics.dll
</pre>

*Important:* Notice that there is an underscore character in the *"_DynaShape"* folder name as shown above. This is to ensure that Dynamo will load DynaShape alphabetically after MeshToolkit. 

Once the package folder has been assembled, you can "install" the package to Dynamo by to *Dynamo-Main-Menu > Settings > Manage Node and Package Paths...*, and add a path to the package folder.

For the mouse interaction to work, for now you will need to manually edit the *AssemblyPath* inside the *DynaShape_ViewExtensionDefinition.xml* file (provided with the Visual Studio solution) so that it points correctly to the *DynaShape.dll* file inside the package folder, and then place this xml into *[DynamoCoreMainFolder]\viewExtensions*, and restart Dynamo Studio and/or Revit

Once the package has been installed, you can start to play with these [Dynamo sample scripts](https://drive.google.com/drive/folders/0B8GXDbjowDN_ZHZ0ZWZaSWIwMzA?usp=sharing) to see how DynaShape works.



## Contact Info
* Email: longnguyen.gigabidea@gmail.com
* Twitter: [@LongNguyenP](https://twitter.com/LongNguyenP?lang=en)



## Acknowledgement
I would like to acknowledge the following people:
* [Ian Kenough](https://twitter.com/ikeough?lang=en) and the [Dynamo](http://dynamobim.org/) development team, for the great visual programming tool.
* The [EPFL Computer Graphics Lab and Geometry Lab](http://lgg.epfl.ch/index.php), for developing the important [theoratical framework](http://lgg.epfl.ch/publications/2012/shapeup/paper.pdf), which DynaShape is based on. 
* [Daniel Piker](https://twitter.com/KangarooPhysics?lang=en), for playing a major role in popularizing physics and constraint-based digital form finding in the design community, mostly via his well-known plugin [KangarooPhysics](http://www.grasshopper3d.com/group/kangaroo.) for Grasshopper. The highly positive response that KangarooPhysics receives from the community has inspired me to start DynaShape in hope to make similar computational design tools available to the Dynamo and BIM community.
* Autodesk (particularly Phil Mueller and Matt Jezyk) for co-organizing and co-sponsoring AEC Hackathon Munich 2017, where DynaShape was born.