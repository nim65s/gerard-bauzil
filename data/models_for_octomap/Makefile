BINVOX=optirun ~/programs/binvox

all: bauzil.bt bauzil.pgm bauzil_freescale.bt bauzil_freescale.pgm

#X3dToVrml97.xslt:
#	wget http://www.web3d.org/x3d/content/X3dToVrml97.xslt -O $@

%.wrl: %.x3d X3dToVrml97.xslt
	xsltproc --output $@ X3dToVrml97.xslt $<

%.binvox: %.wrl
	rm -f $@
	$(BINVOX) -fit -c -d 512 $< | tee tmp
	grep "Mesh::normalize, bounding box: " tmp | sed 's#^[^\[]*\[\([-0-9.]*\), \([-0-9.]*\), \([-0-9.]*\), 1\] - \[\([-0-9.]*\), \([-0-9.]*\), \([-0-9.]*\), 1]#\1 \2 \3 \4 \5 \6#' > $(shell basename $@ .binvox).bb
	rm -f tmp

%.bt: %.binvox
	binvox2bt --mark-free --bb $(shell cat $(shell basename $< .binvox).bb) -o $@ $<


%.pgm: %.bt
	rosparam set makefile_map_server/occupancy_min_z 0.05
	rosparam set makefile_map_server/occupancy_max_z 0.15
	rosrun octomap_server octomap_server_node $< __name:=makefile_map_server &
	rosrun map_server map_saver -f $(shell basename $@ .pgm) map:=projected_map
	rosnode kill makefile_map_server
	sed -i 's#, -nan]#, 0.0]#' $(shell basename $@ .pgm).yaml

clean:
	rm -f bauzil.bt bauzil.binvox bauzil.wrl bauzil.bb bauzil_freescale.bt bauzil_freescale.wrl bauzil_freescale.bb bauzil_freescale.bt

.PHONY: clean

