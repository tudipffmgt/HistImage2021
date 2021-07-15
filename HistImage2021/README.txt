HistImage/
------------------
This dataset contains URLs directing to an entirety of 96 historical images of four landsmarks in the vicinity of Dresden, Germany.
The original data is provided by SLUB Dresden / Deutsche Fotothek (http://www.deutschefotothek.de/) and is not allowed to be shared in social networks like Facebook, Twitter etc.
The images are saved after digitization in full quality as *.jpg files with a maximum edge length of 1600 Px and a maximum sum of both image edges of 2800 pixels using bilinear interpolation in OpenCV.
The orientation of all images is estimated using interactively determined tie points in Agisoft Metashape up to an estimated accuracy of 2 pixels.
A minimum of 15 tie points is given in all images.
The tie points (markers) are given in the Agisoft Metashape .xml export format and are also converted to .h5 files.
This allows the used of the hierarchical localization toolbox (https://github.com/cvg/Hierarchical-Localization) (Sarlin et al., 2020) and the import into COLMAP (https://github.com/colmap/colmap) (Schönberger et al. 2016).
In COLMAP the image orientation can be calculated via bundle adjustment. 
To reproduce the results of the publication it is important to enable two-view-tracks.
This dataset includes the resulting sparse model in .txt files for further processing options.

The purpose of this reference dataset is the evaluation of other feature matching methods.
Additionally, the reference positions can be used to determine the quality of a scene reconstruction, detect outliers and derive error measures.
Also, the methods used in the depicted paper can be reproduced and the dataset can be expanded by own tie points or images to construct more complex models.

Format of .h5 files according to Sarlin et al., 2020:
In a feature file, each key corresponds to the relative path of an image w.r.t. the dataset root (e.g. images/df_hauptkatalog_0008003.jpg for Crowngate), and has one dataset per prediction (e.g. keypoints and descriptors, with shape Nx2 and DxN).
In a match file, each key corresponds to the string path0.replace('/', '-')+'_'+path1.replace('/', '-') and has a dataset matches0 with shape N. 
It indicates, for each keypoint in the first image, the index of the matching keypoint in the second image, or -1 if the keypoint is unmatched.


Directory containing the four different datasets 
Crowngate/ 
Hofkirche/
Moritzburg/ 
Semperoper/ 

and the file you are reading README.txt

Crowngate/
	image_information.txt - .txt file containing the image name, the image size relevant for the tie points, and the permalink for downloading the Crowngate dataset
	matches_hloc/
		Crowngate_features.h5 - All determined tie points in .h5 format
		Crowngate_matches.h5 - All feature matches between all image combinations in .h5 format
		pairs_exhaustive.txt - All possible image pair combinations for the use of the hierarchical localization toolbox
	matches_Metashape_xml/
		Crowngate_markers.xml - Metashape XML Export of all cameras, images and markers; inner orientation of cameras is irrelevant 
	model_COLMAP/
		cameras.txt - Export of COLMAP model file cameras in .txt file format (Camera list with one line of data CAMERA_ID, MODEL, WIDTH, HEIGHT, PARAMS[] per camera)
		images.txt - Export of COLMAP model file image in .txt file format (Image list with two lines of data IMAGE_ID, QW, QX, QY, QZ, TX, TY, TZ, CAMERA_ID, NAME | POINTS2D[] as (X, Y, POINT3D_ID) per image)
		points3D.txt - Export of COLMAP model file points3D in .txt file format (3D point list with one line of data POINT3D_ID, X, Y, Z, R, G, B, ERROR, TRACK[] as (IMAGE_ID, POINT2D_IDX) per point)

Hofkirche/
	image_information.txt - .txt file containing the image name, the image size relevant for the tie points, and the permalink for downloading the Hofkirche dataset
		matches_hloc/
			Hofkirche_features.h5 - All determined tie points in .h5 format
			Hofkirche_matches.h5 - All feature matches between all image combinations in .h5 format
			pairs_exhaustive.txt - All possible image pair combinations for the use of the hierarchical localization toolbox
		matches_Metashape_xml/
			Hofkirche_markers.xml - Metashape XML Export of all cameras, images and markers; inner orientation of cameras is irrelevant 
		model_COLMAP/
			cameras.txt - Export of COLMAP model file cameras in .txt file format (Camera list with one line of data CAMERA_ID, MODEL, WIDTH, HEIGHT, PARAMS[] per camera)
			images.txt - Export of COLMAP model file image in .txt file format (Image list with two lines of data IMAGE_ID, QW, QX, QY, QZ, TX, TY, TZ, CAMERA_ID, NAME | POINTS2D[] as (X, Y, POINT3D_ID) per image)
			points3D.txt - Export of COLMAP model file points3D in .txt file format (3D point list with one line of data POINT3D_ID, X, Y, Z, R, G, B, ERROR, TRACK[] as (IMAGE_ID, POINT2D_IDX) per point)

Moritzburg/
	image_information.txt - .txt file containing the image name, the image size relevant for the tie points, and the permalink for downloading the Moritzburg dataset
		matches_hloc/
			Moritzburg_features.h5 - All determined tie points in .h5 format
			Moritzburg_matches.h5 - All feature matches between all image combinations in .h5 format
			pairs_exhaustive.txt - All possible image pair combinations for the use of the hierarchical localization toolbox
		matches_Metashape_xml/
			Moritzburg_markers.xml - Metashape XML Export of all cameras, images and markers; inner orientation of cameras is irrelevant 
		model_COLMAP/
			cameras.txt - Export of COLMAP model file cameras in .txt file format (Camera list with one line of data CAMERA_ID, MODEL, WIDTH, HEIGHT, PARAMS[] per camera)
			images.txt - Export of COLMAP model file image in .txt file format (Image list with two lines of data IMAGE_ID, QW, QX, QY, QZ, TX, TY, TZ, CAMERA_ID, NAME | POINTS2D[] as (X, Y, POINT3D_ID) per image)
			points3D.txt - Export of COLMAP model file points3D in .txt file format (3D point list with one line of data POINT3D_ID, X, Y, Z, R, G, B, ERROR, TRACK[] as (IMAGE_ID, POINT2D_IDX) per point)

Semperoper/
	image_information.txt - .txt file containing the image name, the image size relevant for the tie points, and the permalink for downloading the Semperoper dataset
		matches_hloc/
			Semperoper_features.h5 - All determined tie points in .h5 format
			Semperoper_matches.h5 - All feature matches between all image combinations in .h5 format
			pairs_exhaustive.txt - All possible image pair combinations for the use of the hierarchical localization toolbox
		matches_Metashape_xml/
			Semperoper_markers.xml - Metashape XML Export of all cameras, images and markers; inner orientation of cameras is irrelevant 
		model_COLMAP/
			cameras.txt - Export of COLMAP model file cameras in .txt file format (Camera list with one line of data CAMERA_ID, MODEL, WIDTH, HEIGHT, PARAMS[] per camera)
			images.txt - Export of COLMAP model file image in .txt file format (Image list with two lines of data IMAGE_ID, QW, QX, QY, QZ, TX, TY, TZ, CAMERA_ID, NAME | POINTS2D[] as (X, Y, POINT3D_ID) per image)
			points3D.txt - Export of COLMAP model file points3D in .txt file format (3D point list with one line of data POINT3D_ID, X, Y, Z, R, G, B, ERROR, TRACK[] as (IMAGE_ID, POINT2D_IDX) per point)

References:
@inproceedings{sarlin2020superglue,
  title     = {{SuperGlue}: Learning Feature Matching with Graph Neural Networks},
  author    = {Paul-Edouard Sarlin and
               Daniel DeTone and
               Tomasz Malisiewicz and
               Andrew Rabinovich},
  booktitle = {CVPR},
  year      = {2020},
}

@inproceedings{schoenberger2016sfm,
    author={Sch\"{o}nberger, Johannes Lutz and Frahm, Jan-Michael},
    title={Structure-from-Motion Revisited},
    booktitle={Conference on Computer Vision and Pattern Recognition (CVPR)},
    year={2016},
}

This work is licensed under CC-BY-SA 4.0 (https://creativecommons.org/licenses/by-sa/4.0/).
This means you are free to share and adapt the data (excluding social networks) under the following terms:
Attribution - You must give appropriate credit, provide a link to the license, and indicate if changes were made. You may do so in any reasonable manner, but not in any way that suggests the licensor endorses you or your use.
ShareAlike - If you remix, transform, or build upon the material, you must distribute your contributions under the same license as the original.
No additional restrictions - You may not apply legal terms or technological measures that legally restrict others from doing anything the license permits.
The original data is provided by SLUB Dresden / Deutsche Fotothek and is not allowed to be shared in social networks like Facebook, Twitter etc.
Metadata is partially provided by SLUB Dresden / Deutsche Fotothek
