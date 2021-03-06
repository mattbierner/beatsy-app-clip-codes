# Beatsy App Clip Codes

App Clip Codes for [Beatsy][app] let you create unique AR music experiences for people to discover in the world. You can use these codes to hype an upcoming musical release or you can design unique auditory and visual experiences for a specific physical space.

<div align="center"> 
    <a href="https://youtu.be/5iWi_Kd7rfw">
        <img src="images/video-thumb.png">
    </a>
</div>

This document covers what you can create using Beatsy App Clip codes. If you would like to create one, please [file an issue][issues] or [reach out][contact] and I will work with you to set one up.

### Table of contents

- [Why Beatsy?](#why-beatsy)
- [Why App Clip Codes?](#why-app-clip-codes)
- [Custom Beatsy app clip codes](#custom-beatsy-app-clip-codes)
- [Visualizer Effects](#visualizer-effects)

## Why Beatsy?

[Beatsy][app] is a free iOS app that distorts the real world with music. Make a wall bulge outward with a bass note or transform a street into a rolling wave of notes.

Beatsy's unique style of AR is eye-catching and fun. While most AR apps simply overlay digital objects onto the real world, Beatsy makes you see and experience the real world differently. It also makes your experience of the music more engaging.

## Why App Clip Codes?

[App clip codes](https://developer.apple.com/design/human-interface-guidelines/app-clips/overview/app-clip-codes/) are QR-style designs that iPhone users can scan to launch a small app experience without having to install anything. Beatsy links these codes to specific audio and augmented reality visualizer effects. When a user scans a Beatsy app clip code, a minimal version of Beatsy will be launched, the linked audio will start playing, and the augmented reality effect will be applied to the real world surface around the code.

You can post App Clip Codes using stickers, posters, or even stencils. With Beatsy, the surface where you place the code on becomes the surface that the music distorts when a user scans the app.

App Clip codes make music discovery interactive and physical. You can tailor individual codes to specific locations or even make finding the codes out in the real world part of the experience.

## Custom Beatsy app clip codes

If you are a musician and would like to create a custom code for Beatsy, just [file an issue][issues] or [let me know][contact]. These codes are free to create and you can use them however you'd like.

The rest of this document covers how you can customize a Beatsy App Clip code and what information I need to create a new code for you. When you reach out, please try to include as much as this information as possible so that we can quickly get a code setup. Don't worry if you aren't sure about some parts though, as I can help walk you through the process.

**Required Info**

- mp3 for the audio. This should be streaming quality (around 192 kbps or so).

    You must also prove that you are the copyright holder of the audio and give me permission to make it available for Beatsy users. 

- Audio title.

    This is displayed in the app when your song is playing and will also be displayed when launching from the app clip.

- Visualizer size in meters.

    This controls how large the visualizer will be. Keep in mind that the visualizer will be displayed at the location of the app clip code in the real world. If you create a 2 meter visualizer for example, make sure any stickers you place for it have at least 1 meter of flat surface around them for the AR effect to be applied properly.

- Visualizer settings.

    Look over the visualizer effects section below and let me know how you'd like to configure the AR visualizer itself. If you are using the `video` visualizer, please also include the video mp4 file.

**Optional Info**

- App clip code colors

    If you are not able to [generate an app clip code yourself](https://developer.apple.com/documentation/app_clips/creating_app_clip_codes/creating_app_clip_codes_with_the_app_clip_code_generator), I can generate a SVG of your app clip code. To do this, I need a foreground and background color to use. Keep in mind that these must be somewhat high contrast so that users can scan them with their phones.

- Song link.

    If provided, Beatsy will show a button in the bottom bar that opens this link. You can use this to link to your homepage or primary social media account, or to a webpage specific to the audio.

- Enable spatial audio?

    If enabled, the music will be played as if it were coming from the position of the visualizer in the world. Spatial audio is disabled by default.

**What you get**

Once everything looks good, I will share a custom app clip code url and App Clip Code image (as an `svg` or `png`) for you to use. You are free to use this image however you'd like. The app clip code will be live as soon as I enter all the info and upload the song.

If you'd like to make any changes to the App Clip after it has been created, please let me know. Be sure to include the url of the App Clip you'd like to change.


## Visualizer Effects

Each app clip can use one of Beatsy's built-in visualizer effects or provide a completely custom experience with a [displacement video](#displacement-video).

Here's a quick overview of the available visualizers effects and how they can be customized:

### Speaker

The speaker visualizer distorts surfaces to make them look like a giant speaker. The distortion responds to the audio, with bass notes causing large, slow moving waves while treble notes create smaller, faster waves.

Try loading your audio up in the [full version of Beatsy][app] to find parameters that work best for it.

**Parameters**

- `amplitude` — The max amplitude (height) of the visualizer.

    This is relative to the visualizer's size. An app clip that sets `position.scale = 3` for example with `amplitude = 0.5`, would be at most 1.5 meters high (`3 * 0.5`).

- `speed` — How fast the waves of the visualizer move. A speed of zero will create standing waves.

### Wave

The wave visualizer distorts surfaces by creating a wave of notes. The center part of the wave shows the most recent musical sample, broken down into base, middle, and high notes. Over time, the samples flow outwards towards the edges of the visualize.

Try loading your audio up in the [full version of Beatsy][app] to find parameters that work best for the wave visualizer.

**Parameters**

- `amplitude` — The max amplitude (height) of the waves.

    This is relative to the visualizer's size.

- `historySize` — How much history is shown in the wave at a time.

    With `historySize` of 30 for example, the last 30 samples of music (about one second worth) will appear in the wave. The most recent entries always appear towards the center, with older ones flowing out towards the edges.

### Ferro

The ferro visualizer is based on magnetic fluid and distorts surfaces using bulges that respond to the music.

Try loading your audio up in the [full version of Beatsy][app] to find parameters that work best for it.

**Parameters**

- `bulgeSize` — The size of the central bulge.

    This bulge rises from the center of the visualizer. All the smaller bumps sprout off of it. The central bulge is what gives the effect more three dimensional look.

    If you set this to zero, then the small bumps will still show up but they will appear as if they were on a flat plane.

- `numberOfBands` — The number of bands of small bumps. Should be between 1 and 4.

    The small bumps run concentrically around the central bulge. They are split into a set number of bands, each one which responds differently the music. The inner bands of bumps respond to higher notes, while outer bands respond to low notes.

- `speed` — The rotation speed of the small bumps.

    If you set this to zero, the bumps will be fixed in place instead of rotating around the visualizer.

- `bumpSize` — The size of the small bumps.

### Displacement Video

A displacement video lets you create fully custom visualizations specifically for your audio. It uses a [displacement map](https://en.wikipedia.org/wiki/Displacement_mapping) to distort the surface, enabling arbitrary visual effects.

**Parameters**

- `amplitude` — The max amplitude (height) of displacement for the visualizer.

    This is relative to the visualizer size. A visualizer that is 3 meters in size with `amplitude = 0.5` for example, would be at most 1.5 meters high (`3 * 0.5`). This maximum displacement would only be reached for pure white pixels. Grey pixels would have intermediate displacements, while pure black pixels will be undistorted. 

**Video**

Each pixel in the video specifies how far that part of the surface will be shifted upwards by the AR effect. Parts of the plane under black pixels will have zero displacement, while parts under white pixels will be displaced to the maximum visualizer height (which is controlled by the `amplitude`). Grey pixels will have intermediate levels of displacement.

Here's an example displacement video along with the resulting effect:

<div align="center"> 
    <a href="https://youtu.be/J3X7MX8xeNk">
        <img src="images/displacement-video-thumb.png">
    </a>
</div>

The simplest way to generate a displacement video is with a 3D rendering program. Instead of rendering color for a scene, you'd render the depth buffer (clamping the interesting depth range between 0 and 1). You can also capture depth information using a LiDAR sensor, or even create the depth video by hand if you are feeling ambitious.

Some details on the video file video:

- Mp4.
- Monochrome.
- Square of around 400x400px.
- No audio.

If the displacement video is shorter than the song, the video will loop during playback. You can use this to loop a short seamless animation.

## Next Steps

If using [Beatsy][app] with your music sounds interesting, please [file an issue][issues] or [reach out][contact] and I will work with you to create your custom app clip code.



[app]: https://apps.apple.com/us/app/beatsy/id1543162330
[contact]: https://blog.mattbierner.com/about/
[issues]: https://github.com/mattbierner/beatsy-app-clip-codes/issues