# THD Improved Battle Damage - Blood and Bones DLC
![Alt text](Example_Images/Thumbnail.png "a title")

**DISCLAIMER** - This mod is intended for <Prismatic Blood> to be enabled for the Blood and Bones DLC. It can work with it off, but the overlays will no longer match the unit blood and won't look look as well.

**Description:** This mod performs 2 things. First, every myth unit and some heroes have been assigned a specific prismatic blood color for their bloodpools and sprays, with the majority of myth units being assigned to red blood by default. Second, the <Bloodied Units> damage overlay has been revamped for the following:

    * Blood damage now matches the blood color for each unit
    * Weapons, shields, some helmets, and other non-body equipment (i.e. chariots and carts) for both human and myth units have been assigned a "grey" damage color to represent battle wear and tear.
        * These will no longer be covered in blood by damage

This mod is compatible with my other bloodpools mod.


**Changelog**

v 1.0

    * Added 8 new damage overlays of different colors
    * Explicitly assigned blood colors to every myth unit and some heroes. 
        * Majority of myth units have red blood now by default as group, mythbloodred. Game has this set to random previously
    * Assigned a specific damage overlay color to each relevant myth and hero unit's model .MATERIAL, rather than the default red
        * Some multi-model units have different simultaneous overlays, i.e. Bellerophon and his pegasus each have different blood colors
    * Assigned a "grey" damage overlay to all weapons, shields, separate helmets, and other non-body unit equipment .MATERIAL files. This allows for a grey overlay to appear on these items upon damage instead of the unit's normal blood.
    * A total of 628 .MATERIAL files were modified
    
**Documentation**:

In Data.bar
[blood.xml] - declares all the <bloodgroup> objects with the colored blood pools and their skeletons assigned

[proto.xml] - unit attributes, added a new attribute <bloodgroupoverride>mythblood______</bloodgroupoverride> (______ insert color of choice here)

In Art<insert_civ>.bar
[______.material] - (___ insert unit name or attachment here) the material that is inhereted from the <opaque_lit> parent class. The attribute of interest here is <texture name="Blood Texture" override="bloodpack\vfx\decal\overlay\textures\blood_overlay_small_01_basecolor"></texture>. This assigns the blood overlay texture, which I instead map to one of my choice.

    blood_overlay_small_01_green_basecolor
    blood_overlay_small_01_blue_basecolor
    blood_overlay_small_01_purple_basecolor
    blood_overlay_small_01_yellow_basecolor
    blood_overlay_small_01_whitegold_basecolor
    blood_overlay_small_01_rainbow_basecolor
    blood_overlay_small_01_grey_basecolor
    blood_overlay_small_01_gold_basecolor

Because each unit and their attachment .MATERIALs had to be modified separately, future changes will be a little laborious. Maybe if these overlays can be mapped at the <bloodgroup> level from the blood.xml file, and maybe the equipment be mapped as a group somehow, that could streamline this whole process. That likely would have to come from the developers.


