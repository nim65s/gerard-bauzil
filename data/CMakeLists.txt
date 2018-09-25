#
#  Copyright CNRS
#
#  Author: Olivier Stasse
#
SET(${PROJECT_NAME}_GBDATA
  AluminumChair.dae
  AluminumChair.obj
  AluminumChair.wrl
  armoire.dae
  armoire.obj
  armoire.wrl
  barrier.dae
  barrier.obj
  barrier.wrl
  barrier_v2.dae
  Bauzilv6.dae
  beam-30cm.dae
  blue-column.dae
  blue_column.mtl
  blue_column.obj
  blue_column.wrl
  blue_column2.wrl
  blue_column3.wrl
  box-steppingstones.wrl
  cobblestone.dae
  cylinder.dae
  desktop_v2.obj
  desktop.wrl
  door.obj
  door-v2.obj
  drawers.obj
  drawers.wrl
  estrade.dae
  estrade.obj
  estrade_v2.dae
  estrade.wrl
  laas_gerard_bauzil.wrl
  longfloor.wrl
  placard.obj
  placard.wrl
  poutre15.obj
  poutre15.wrl
  poutre20.obj
  poutre20.wrl  
  poutre30.obj
  poutre30.wrl
  staircases_koroibot.dae
  staircases_koroibot_handrail.dae
  staircases_koroibot_handrail.mtl
  staircases_koroibot_handrail.obj
  staircases_koroibot_hr.dae
  staircases_koroibot_hr.mtl
  staircases_koroibot_hr.obj
  staircases_koroibot_hr.wrl
  staircases_v2.dae
  staircases_v3.dae
  stairs.wrl
  steppingstones.dae
  steppingstones.mtl
  steppingstones.obj
  steppingstones_v2.dae
  wall_laas8.obj
  wall_laas9.dae
  wall_laas9.obj
  wall_laas9.wrl
  wall_laas11.dae
  wall_laas11.obj
  wall_laas12.dae
  wall_laas12.obj
  wall_laas13.dae
  wall_laas15.blend
  wall_laas15.dae
  wall_laas15.wrl
)

SET(${PROJECT_NAME}_FULLPATHDATA )
FOREACH (ldata ${${PROJECT_NAME}_GBDATA})
  SET(${PROJECT_NAME}_FULLPATHDATA
    ${${PROJECT_NAME}_FULLPATHDATA} 
    ${CMAKE_CURRENT_SOURCE_DIR}/${ldata})
ENDFOREACH(ldata)

INSTALL(FILES ${${PROJECT_NAME}_FULLPATHDATA}
  DESTINATION share/${PROJECT_NAME}
  PERMISSIONS OWNER_READ GROUP_READ WORLD_READ OWNER_WRITE
)
