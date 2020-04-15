---
layout: page
title: Audio Field
category: [field]
---

The audio field is used for recording audio with your device's microphone.  While recording, Flexile can pause & resume recording.  Flexile can record separate segments (stop and start instead of pausing) and it can delete individual segments if needed.  Flexile can also append a new recording to an old one.

The audio field also features a wave form graph that can help navigate a recording visually.  This can be especially helpful if you've got a long recording.

## Audio Interface
### The Audio Graph
The audio graph is presented after you've started playback or recorded an audio session.  It represents a sampling of the recording you've made as a graphical representation of the audio.  While the control is playing back the audio, you can tap on the graph to change the position of the playback.  As a side note: In long recording, it may not be easy to find what you're looking for, but the audio graph can help you get a rough idea of where you might look.  After changing the audio position, use the Forward and Back buttons (explained below) to fine tune the playback position.

### Record Button
The record button has multiple uses, depending on what state the audio field is in.  If the field has not been opened for editing, tapping on the record button will open the field for editing (it'll display in full screen).  Once you've opened the field for editing, tapping on the record button will start the device recording.  While audio is being recorded, the record button will glow a brighter red than normal.  You can also stop the audio recording by tapping on the record button while the device is recording.

### Play Button
The play button does exactly what you'd think: It starts playing back the recording at the current position.  You can tell the where the audio position is both by the time label in the lower left of the audio graph as well as the progress overlay on top of the audio graph.

### Pause Button
The pause button will pause whatever the audio control is doing at the moment.  If you're currently playing back audio, the pause button will be displayed so that you can pause it.  If you're recording, again the pause button will be displayed so that you can pause the recording.  Note that pausing a recording doesn't end a recording session like tapping the Stop or Record button will.  If you press the record button after pausing a recording, the recording will continue like normal.

### Forward Button
You can tap on the forward button to progress the playback forward by 5 seconds.  This only really has an effect on playing back audio.  This can be really useful if you're trying to find a particular spot in the audio recording.

### Back Button
You can tap on the back button to progress the playback backward by 5 seconds.  This also only has an effect on playing back audio.  This can be really useful if you're trying to find a particular spot in the audio recording.

### Stop Button
The stop button will stop either the playback or the recording.  If you stop the playback, the audio position will return to the beginning of the recording.  If you stop a recording, that will end the current recording session and complete a section.  Start recording again and a new session will be created and appended to the current set of audio sections.

### Trash Button
After you've added a recording session, you can tap on it to select it (this only works while the field is in editing mode fullscreen).   A selected session will have a red overlay.  You can then tap on the trash button to delete it.  Warning: Deletion is permanent.

### Mic
Similar to the recording button, you can tap anywhere on the mic to begin and stop an audio recording. The mic will also display the meter level (shown in red) of the received audio and can help you get an idea of the recording volume. 

## Saving Audio
When you're done recording audio, you can save it along with the rest of the record. However, even though you can leave the record, Flexile may take a little bit to actually write the audio file to disk, and if you try to play the recording before Flexile has had a chance to finish writing the file, you'll get an error.  In most cases this won't be a problem, but Flexile doesn't limit the size of your recordings so it's possible that this process could take a little while.  For this reason, there is a setting (In Flexile's main "Settings") called "Audio Alert".  If you select this, Flexile will post an alert whenever it finished writing an audio file to disk.

How long it take Flexile to write an audio file will depend on the device, but I've found a 30 minute recording can take about 10-20 seconds to write to disk.  Of course, if your recording hours of audio, it could take a few minutes.  Hopefully, that'll give you an idea of what to look for. 