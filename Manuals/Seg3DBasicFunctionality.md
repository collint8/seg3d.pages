---
title: Seg3D Basic Functionality
category: documentation
layout: default
---

Contents
========

[1 Overview](#overview)   
..[1.1 About Seg3D](#about-seg3d)  
..[1.2 Software Requirements](#software-requirements)  
....[1.2.1 Seg3d](#seg3d)  
[2 Welcome Screen](#welcome-screen)  
..[2.1 Load Recent Project](#load-recent-project)  
..[2.2 Open Existing Project](#open-existing-project)  
..[2.3 Start New Project](#start-new-project)  
..[2.4 Quick Open File](#quick-open-file)  
..[2.5 Quit](#quit)  
[3 Seg3D Viewer](#seg3d-viewer)  
..[3.1 Controlling Windows](#controlling-windows)  
..[3.2 Viewer Panels](#viewer-panels)  
....[3.2.1 2D Slice Viewer](#d-slice-viewer)  
....[3.2.2 3D Volume Viewer](#d-volume-viewer)  
..[3.3 Tool Bar](#tool-bar)  
..[3.4 Viewing Options](#viewing-options)  
....[3.4.1 Full Screen](#full-screen)  
....[3.4.2 One Viewer](#one-viewer)  
....[3.4.3 One and One](#one-and-one)  
....[3.4.4 One and Two](#one-and-two)  
....[3.4.5 One and Three](#one-and-three)  
....[3.4.6 Two and Two](#two-and-two)  
....[3.4.7 Two and Three](#two-and-three)  
....[3.4.8 Three and Three](#three-and-three)  
....[3.4.9 Table of Shortcuts](#table-of-shortcuts)  
[4 Seg3D Windows](#seg3d-windows)  
..[4.1 Project Window](#project-window)  
..[4.2 Tools Window](#tools-window)  
..[4.3 Layer Manager Window](#layer-manager-window)  
..[4.4 Volume View Window](#volume-view-window)  
....[4.4.1 Fog Panel](#fog-panel)  
....[4.4.2 Clipping Planes Panel](#clipping-planes-panel)  
....[4.4.3 Volume Rendering Panel](#volume-rendering-panel)  
....[4.4.4 Rendering Options](#rendering-options)  
....[4.4.5 Transfer Function](#transfer-function)  
..[4.5 Provenance Window](#provenance-window)  
..[4.6 Controller Window](#controller-window)  
....[4.6.1 Actions Tab](#actions-tab)  
....[4.6.2 State Variables Tab](#state-variables-tab)  
...[4.6.3 Event Log Tab](#event-log-tab)  
....[4.6.4 Undo/Redo Buffer Tab](#undoredo-buffer-tab)  
..[4.7 Python Console](#python-console)  
..[4.8 Message History Window](#message-history-window)  
[5 Basic Program Functions](#basic-program-functions)  
..[5.1 File](#file)  
....[5.1.1 New Project](#new-project)  
....[5.1.2 Open Project](#open-project)  
....[5.1.3 Show Project Folder](#show-project-folder)  
....[5.1.4 Save Project](#save-project)  
....[5.1.5 Save Project As](#save-project-as)  
....[5.1.6 Launch Another Copy of Seg3D](#launch-another-copy-of-seg3d)  
....[5.1.7 Import Layer From Single File](#import-layer-from-single-file)  
....[5.1.8 Import Layer From Image Series](#import-layer-from-image-series)  
....[5.1.9 Export Segmentation](#export-segmentation)  
....[5.1.10 Export Active Data Layer](#export-active-data-layer)  
....[5.1.11 Recent Projects](#recent-projects)  
..[5.2 Edit](#edit)  
....[5.2.1 Undo](#undo)  
....[5.2.2 Redo](#redo)  
....[5.2.3 Copy Mask Slice](#copy-mask-slice)  
....[5.2.4 Paste Mask Slice](#paste-mask-slice)  
....[5.2.5 Punch Through Volume](#punch-through-volume)  
..[5.3 Help](#help)  
....[5.3.1 Search](#search)  
....[5.3.2 Keyboard Shortcuts](#keyboard-shortcuts)  
..[5.4 Preferences](#preferences)  
....[5.4.1 General](#general)  
....[5.4.2 View](#view)  
....[5.4.3 Layers](#layers)  
....[5.4.4 Sidebars/Tools + Filters](#sidebarstools--filters)  

1 Overview
==========

This document is meant as a basic reference and walkthrough of the Seg3D layout and functionality. Specifically, every feature of the software will be addressed in a brief manner. Tool and filter documention are found in the [Seg3d Tool Documentation](../tools.md)

Note: If you are looking for a refresher on the available keyboard and mouse shortcuts, there is a list under the **Help** menu of the Seg3D.

1.1 About Seg3D
---------------

<figure>
  <img src="Seg3DBasicFunctionality_figures/layout.png" id="layout">
  <figcaption>Figure 1.1 Seg3D in use.</figcaption>
</figure>

Seg3D is a lightweight software tool developed for use in visualizing and segmenting image data. The core intended use of Seg3D involves loading 3D scalar data, such as MRI or CT scans, and generating labels mask to identify various regions of interest in the original image data. Seg3D facilitates the process using interactive tools such as image processing filters and manual masking techniques.

In addition to manual segmenting, the current version of Seg3D includes some features that facilitate automated segmenting. Provenance is a recently added feature which tracks the steps used to create label masks. This feature allows the user to then repeat the same sets with different parameters using the Python and Controller windows. Future extensions of these capabilities will allow for scripting in the terminal and porting to other programs such as SCIRun and VisTrails.

Seg3D is an crucial element of our software suite also involving BioMesh3D and SCIRun that make possible the development of image based computational models. Label masks generated with Seg3D are used in other software for such applications as 3D visualization or computational modeling. BioMesh3D requires a segmentation like those from Seg3D to generate high quality, multi-material computational meshes. SCIRun is a modular problem solving environment that generates and runs visualization and simulation tasks on segmentations from Seg3D and meshes from BioMesh3D. This interaction makes Seg3D a key step in image based modeling.

1.2 Software requirements
-------------------------

### 1.2.1 Seg3D 

Seg3D is distributed as a binary download for Linux, Windows, and OS X. Please visit the [SCI software portal](https://github.com/SCIInstitute/Seg3D.git) to download the latest Seg3D binary.

2 Welcome Screen
==============

Anytime you start Seg3D, users are first presented with the Seg3D welcome screen. As seen in <a href="#welcome">Figure 2.1</a>, the welcome screen consists of the Seg3D splash screen and a menu displaying the available options for starting and continuing a segmentation in Seg3D. The included options are to load a recent project, open existing project, start a new project, quickly open a file for viewing, and to quit Seg3D. These options are the same as some of the options in the **File** menu which are explained in this chapter as well as [Sec. 5.1](#file).

<figure>
  <img src="Seg3DBasicFunctionality_figures/welcome_screen.png" id="welcome">
  <figcaption>Figure 2.1 Seg3D welcome screen.</figcaption>
</figure>


3 Seg3D Viewer
============

The Seg3D viewer is the main interface between the users and the software. This viewer is meant to be highly interactive and intuitive. Using a combination of mouse functions, keyboard shortcuts, and visual buttons the users can quickly visualize and segment data. This chapter will describe the functionality of several aspects of the Seg3D viewer including the overall layout of the interface, 2D slice viewer, 3D volume viewer, and the various viewing options available.

<figure>
  <img src="Seg3DBasicFunctionality_figures/layout_blank.pdf" id="blank">
  <figcaption>Figure 3.1 Seg3D interface.</figcaption>
</figure>

The default layout when Seg3D is opened and a new project is created is shown in <a href="#blank">Figure 3.1</a>. As seen from the image the interface for Seg3D consists of a number of viewers (both 2D and 3D), windows to control the functionality of Seg3D, and a tool bar at the bottom of the screen.


4 Seg3DWindows
=============

In addition to the viewer windows discussed in the above chapter, there are several other windows involved in streamlining the user interface of the Seg3D software. Each of these windows can be accessed through the ’Window’ drop-down menu. By default these windows appear in certain positions defined below, but each can be undocked from the Seg3D interface and either left as stand alone windows or repositioned elsewhere on the Seg3D application (see [Sec. 3.1](#controlling-windows)).

4.8 Message History Window
--------------------------

The Message History Window is not opened by default when Seg3D is opened. This window is opened by clicking on the message history icon in the bottom left of the screen in the tool bar ([Table 3.7](#toolbaricons)). This window will show the messages that Seg3D displays when many functions are performed. This can be used to track your steps at a high level.

5 BasicProgramFunctions
=========================

This section gives a brief overview of the options found under the File, Edit, and Help menus. These menus contain options that allow you to save and open new projects, and set preferences.
