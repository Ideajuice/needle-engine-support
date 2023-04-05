---
lang: en-US
title: Getting Started
next: deployment.md
---

# Getting started 🎈

To get an idea for what kind of things are possible using Needle Tools, check out the  [Samples and Modules](./samples-and-modules.md).  

Once you're ready to start your own project, the steps below will get you started with **Needle Engine** and **Needle Tools for Unity**.  
After following them, you'll have a fully functional project.
From there, you can dive deeper into [Scripting](./scripting.md), [VR and AR](./xr.md) or [Networking](./networking.md)

## Get Ready

The first set of instructions is the same no matter if you want to start with one of our scene
templates, one of our sample projects, or create your own needle tools based app from scratch.

1. **Make sure node.js and Unity are installed - <a href="#prerequisites">see details</a>**  

2. **Create a new Unity project**  
  Open Unity Hub and create a new project. 2021.3 recommended!  
  Make sure to switch it to Linear color space in `Project Settings > Player`.
  
3. **Download our installer**  
    <needle-button href="https://engine.needle.tools/downloads/unity"><strong>Download Needle Engine for Unity</strong></needle-button>  • [Alternative](https://package-installer.glitch.me/v1/installer/needle/com.needle.engine-exporter?registry=https://packages.needle.tools&scope=com.needle&scope=org.khronos)   

    Our installer is a `.unitypackage` that will set everything up for you. It is very small, and it rarely changes. It contains just enough code to download and install Needle packages from our code registry. 
  
4. **Install by dropping into Unity**   
   Drop the downloaded `.unitypackage` file into a Unity project and confirm that you want to import it.  
   This will download the latest version of Needle Engine and Needle Tools for Unity directly from our custom package registry.

5. **Wait for the installation to finish**  
   You may have to click _Assets > Refresh_ once or focus another app and then focus Unity again.  
     > **Note**: A window may open stating that "A new scoped registry is now available in the Package Manager.". This is our Needle Package registry where packages are downloaded from. You can safely close that window.  


## Collab Sandbox Showcase ⚡

The collaborative sandbox example will show you how to quickly get a Needle Tools site up and running with all of the advanced components included. Watch our Getting Started video and follow along with the instructions below to build a fully functional networked example 😊   
<video-embed src="https://www.youtube.com/watch?v=3dB-d1Jo_Mk" limit_height />

1. **Create a new scene from the Collab Sandbox template**  
   Select _File > New Scene_ and choose from one of the Needle templates.  
   We recommend the [Collab Sandbox](https://needle-tiny-starter.glitch.me/) template which is a great way to get started with interactivity, multiplayer, and adding assets.  

2. **Continue [here](#generate-a-web-project-and-add-content)** to learn how to build and deploy the project, then return here to continue with a more in depth look at how to build a Needle Tools app from scratch.

⭐ **Congratulations!**  You just started your first project using Needle Engine! We're excited what you'll build.  
Next we will show you how to generate a new project from scratch and show you the steps below to add your own custom content.

### Create a new scene from a Scene Template

1. Follow the steps in the Get Ready section to set up your project as a Needle Tools project.

We provide a number of Scene Templates for quickly starting new projects.  
These allow you to go from idea to prototype in a few clicks.  You can
use one of the scene templates by following the steps below.

1. Click on `File > New Scene`
2. Select one of the templates with (needle) in their name and click `Create`.
3. **Continue [here](#generate-a-web-project-and-add-content)**.

![20220822-140539-wqvW-Unity_oC0z-needle](https://user-images.githubusercontent.com/2693840/185917275-a147cd90-d515-4086-950d-78358185b1ef.png)

### Create a new scene from scratch

To create a scene from scratch, you can follow these steps.  
Effectively, we're going to recreate the "Minimal (Needle)" template that's shipping with the package.  

1. **Create a new empty scene**  

2. **Set up your scene for exporting**   
  Add an empty GameObject, name it "Exporter" and add an `ExportInfo` component to it.  
  In this component you create and quickly access your exported runtime project.  
  It also warns you if any of our packages and modules are outdated or not locally installed in your web project.  

::: tip Note
By default, the project name matches the name of your scene. If you want to change that, you can enter a ``Directory Name`` where you want to create your new runtime project. The path is relative to your Unity project.  
:::
 
3. **Choose a web project template**  
  Now, select a web project template for your project. The default template is based on [Vite](https://vitejs.dev/), a fast web app bundler.  

4. **Continue [here](#generate-a-web-project-and-add-content)** to learn how to build and deploy the project, then return here to continue with a more in depth look at how to build a Needle Tools app from scratch.

5. **Add content**    
   1. Create a new empty GameObject
   1. Add a ``GltfObject`` component to it. This component marks parts of your hierarchy to be exported as glTF file. 
   1. Add an object (e.g. ``Create/3D Object/Cube``) as a child to the ``GltfObject`` hierarchy and save. 
   1. Your browser should refresh and your object is visible.

6. **Make it interactive**  
  Needle Engine comes with a set of [prebuilt components](./component-reference.md) that you can use to easily make your scene interactive. One of those components is ``OrbitControls``, which we're going to use to make the camera interactive.
    1. Select your ``Main Camera`` GameObject
    1. Add a new ``OrbitControls`` component to it 
    1. Press play or save your scene
    1. Your browser should refresh and you can now move the camera around.

::: tip Note    
**The local server does not start / no website in your browser?**  
  Make sure you read and followed the [Prerequisites](#prerequisites-).  
  Also check the console and `ExportInfo` component for warnings or errors.   
  And last but not least, press `Play` to start the local server.  
:::
  

::: tip Note    
**No cube on your website?**   
  Make sure it's a child of your GltfObject root.  
:::

------------
## Generate a web project and view it in a browser

Needle Engine is a web-based runtime, and so there's always two projects: your Unity project and a web project that contains regular HTML, Jaascript, Typescript and CSS. Needle Exporter brings these together into a fast, iterative workflow.  
Usually, one Unity Scene with `ExportInfo` has one web project, so we're going to generate one now.  

1. **Generate your web project**   
  On the `ExportInfo` component, click ``Generate Project``.   
  Wait a moment for the installation to finish — you can see a progress indicator in the bottom right corner of the editor.  

2. **View your project in a browser**
  After a few seconds of installation, your project should automatically run and a new browser window opens. 
  
::: tip Note
You might see a warning in your browser about SSL Security depending on your local configuration.  
This is because while the connection is encrypted, by default there's no SSL certificate that the browser can validate.  
If that happens: click ``Advanced`` and ``Proceed to Site``. Now you should see your scene in the browser!  
:::

::: tip Note    
Keep an eye for console warnings! We log useful details about recommended project settings and so on. For example, your project should be set to Linear color space (not Gamma), and we'll log an error if that's not the case.  
:::


------------

## Prerequisites 💿

Below each tool, you find quick links to download the latest version at the time of writing.  

### Install these tools for development

  [**Node.js** (16.x or 18.x)](https://nodejs.org/en/) – for running a local development server (required)   
  [Windows 16.7](https://nodejs.org/dist/v16.17.0/node-v16.17.0-x64.msi) • [MacOS Universal](https://nodejs.org/dist/v16.17.0/node-v16.17.0.pkg)  
  
  <!--
  [**git**](https://git-scm.com/downloads) – for downloading packages from GitHub (required)  
  [Windows](https://git-scm.com/download/win) • [MacOS Universal](https://git-scm.com/download/mac)  
   -->
  
  [**VS Code**](https://code.visualstudio.com/) – for code editing (recommended)  
  [Windows](https://code.visualstudio.com/sha/download?build=stable&os=win32-x64-user) • [MacOS Universal](https://code.visualstudio.com/sha/download?build=stable&os=darwin-universal)  
  
  [**Unity** 2020.3.16+, 2021.3+ or 2022.2+](https://unity3d.com/get-unity/download) – for setting up your scene and components  (required)  
  _Universal Render Pipeline or Built-In Render Pipeline_  
  _Linear Colorspace_
  
### Install these tools for production builds

  [**toktx** 4.1](https://github.com/KhronosGroup/KTX-Software/releases/tag/v4.1.0-rc3) – for texture compression (recommended)   
  [Windows x64](https://fwd.needle.tools/needle-engine/toktx/win) • [MacOS x64](https://fwd.needle.tools/needle-engine/toktx/osx) • [Mac OS with Apple Silicon](https://fwd.needle.tools/needle-engine/toktx/osx-silicon) • [Other](https://github.com/KhronosGroup/KTX-Software/releases/tag/v4.1.0-rc3)    
 
After installing the tools above, you might have to restart your machine so that all environment variables are properly updated.  

<!--
## Option 1: Quick Start — Starter Project ⚡
1. **Download or Clone this repository**  
   It's set up with the right packages and settings to get you started right away.  

   _Clone with HTTPS:_ ``https://github.com/needle-tools/needle-engine-support.git``  
   _OR clone with SSH:_ ``git@github.com:needle-tools/needle-engine-support.git``  
   _OR download directly:_ <a href="https://github.com/needle-tools/needle-engine-support/archive/refs/heads/main.zip" target="_blank">Download Repository</a>
   
  
2. **Open the starter project**  
  Open `starter/Needle Engine Starter 2020_3` for a full sandbox project that's ready to run (including a couple of simple example scenes for lightmaps and custom shaders).  
  This is a sandbox builder project! It already comes with multi-player capabilities, and works across mobile, desktop, VR and AR.  

3. **Press Play**  
  Make sure the scene CollaborativeSandbox is open, and press Play! This will automatically do some setup steps and start a local server.  
  Once the setup is complete, a browser window will open, and your project is live.  
  From now on, all changes you do in Unity will be immediately visible in your browser.  

    > **Note**: Your browser might warn you about an untrusted SSL connection. Don't worry, the connection is still encrypted – please click "Advance" if your browser asks you to verify that you're sure you want to visit your server.  

4. **Make it your own**  
  Add assets and components, play around with lighting, add scripts and logic – this is your world now!  
  You can also [publish it on the web for free](#deploy-your-project-to-glitch-) so that others can join you.  
-->

## What's next?

👉 Continue reading about [exporting 3D objects and content](./export.md), [scripting](./scripting.md) or learn about how to [deploy your website to the web](./deployment)!

In case you need more troubleshooting help, please see the [Questions and Answers](./faq.md) section.  
You can also join our [Discord Community](https://discord.needle.tools)!
