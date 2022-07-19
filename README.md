# kicad-util .jar build

There are multiple panelizers available for KiCad, but only one is suitable for easily placing multiple oddly-shaped PCBs onto a panel: the [kicad-util panelizer](https://gitlab.com/dren.dk/kicad-util).

You simply place the PCBs next to each other and draw lines between them on the Eco1.User layer. Then run a kicad-util command voila; the lines are transformed into mouse-bites.

Unfortunately, kicad-util is not compatible with the updated PCB format of KiCad 6, so the drawn lines are not converted to mouse bites anymore.

Luckily, [a merge request](https://gitlab.com/dren.dk/kicad-util/-/merge_requests/1) contains the fix, but the kicad-util creator is not available anymore. Although the contributor created [his fork](https://gitlab.com/markxr/kicad-util), the .jar file is not recompiled, so the fixed version is still quite inaccessible for most users.

Given the above, I recompiled the fixed kicad-util version with the `mvn package` command and made [the .jar file](https://github.com/mondalaci/kicad-util-jar/raw/main/kicadutil.jar) available. I use it as:

`java -jar ~/bin/kicadutil.jar pcb -f=myboard.kicad_pcb panel --inset=0 --hole=0.35 --pitch=0.7 --width=2.5 --fillet=1`

