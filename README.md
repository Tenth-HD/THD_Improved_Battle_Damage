# THD Improved Battle Damage - Blood and Bones DLC
![Alt text](Example_Images/Thumbnail.png "a title")

**DISCLAIMER** - This mod is intended for <Prismatic Blood> to be enabled for the Blood and Bones DLC. While it can work with it off, the overlays will no longer match the unit blood and won't look as well.

**Description:** This mod performs 2 things. First, every myth unit and some heroes have been assigned a specific prismatic blood color for their bloodpools and sprays, with the majority of myth units being assigned to red blood by default. Second, the <Bloodied Units> damage overlay has been revamped for the following:

    * Blood damage now matches the blood color for each unit
    * Weapons, shields, some helmets, and other non-body equipment (i.e. chariots and carts) for both human and myth units have been assigned a "grey" damage color to represent battle wear and tear.
        * These will no longer be covered in blood by damage

This mod is compatible with my other bloodpools mod.


Example Images:
![Alt text](Example_Images/Example_Greek_Human_Damage2.png "Greek Hoplite Example")

![Alt text](Example_Images/Example_Norse_Human_Damage2.png "Norse Humans")

![Alt text](Example_Images/Example_Green_Damage2.png "Manticores")

**Changelog**

v 1.1

    * Fixed mispelling in proto.XML causing error messages
    * Changed the yellow blood overlay to be more subtle
    * Added crackles to grey texture and readjusted coloring
    * Crackle effect was added to overlay mask to adjust damage appearance
    * Added the item battle damage to Achilles' helmet
    * Removed overlay from Shinigami as this caused missing textures
    
v 1.0

    * Added 8 new damage overlays of different colors
    * Explicitly assigned blood colors to every myth unit and some heroes. 
        * Majority of myth units have red blood now by default as group, mythbloodred. Game had this set this to random colors previously
    * Assigned a specific damage overlay color to each relevant myth and hero unit's model .MATERIAL, rather than the default red
        * Some multi-model units have different simultaneous overlays, i.e. Bellerophon and his pegasus each have different blood colors
    * Assigned a "grey" damage overlay to all weapons, shields, separate helmets, and other non-body unit equipment .MATERIAL files. This allows for a grey overlay to appear on these items upon damage instead of the unit's normal blood.
    * A total of 628 .MATERIAL files were modified

**Credits**

CryShana for their .BAR editor tool https://github.com/CryShana/CryBarEditor
KJohnHayes - For Myth unit blood color suggestion spreadsheet https://forums.ageofempires.com/t/blood-and-bones-pack-feedback/284996/21

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


