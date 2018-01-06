---
title: NUMB Soundboard
order: 2014-05
thumbnail: numb_soundboard/numb_thumbnail.jpg
client: Goat in the Road Productions
repo: https://github.com/darthmall/Dinglake
abstract: >-
  An application for triggering sound effects with a MakeyMakey during performances of Goat in the Road's play, NUMB.
---

![A promo photo of the cast of NUMB around the table built specifically for triggering sound effects during performances]({% link assets/img/numb_soundboard/numb.jpg %})

## Theater Tech

[Goat in the Road's][grp] [NUMB][numb] is a spartan production relying on six actors, a few chairs, a table, a handful of props, and sound to transport the audience back in time to the days just before anesthetics were introduced into surgery. As part of his award-winning sound design, my brother, [Kyle][kcs], connected several of these props to a [MakeyMakey][makey] with a bluetooth connection to his laptop in the sound booth so that the actors could trigger the sound effects themselves on stage.

I helped him write a simple soundboard application that mapped one or more sounds to the key codes sent by the MakeyMakey. Each time an actor triggered one of the sounds, the application would play one of the sounds mapped to that key, making sure to repeat sounds as little as possible. The application included a minimal interface for monitoring and interrupting playback so that Kyle had control from the sound booth.

## Dinglake UI

![A screenshot of the soundboard playing a sound effect of someone pouring wine]({% link assets/img/numb_soundboard/wine_pour.png %})

Because the application was designed for use during live performances, I kept it dark so that it wouldn't create a distracting glow in a dark theater or ruin Kyle's night vision. It presents a simple UI that indicates which sound effects are mapped to which keys for setup and testing. To facilitate monitoring during performances, the currently playing effect is highlighted and the top of the UI shows a progress bar for the currently playing sound effect. In case an effect was triggered by accident, there's a stop button shown next to each effect while it's playing.

The application was configured using a [JSON file][config] that mapped an array of sound files to a key, making it easy to add, remove, or reorder sounds without having to make any changes to the software.

[grp]: http://www.goatintheroadproductions.org
[numb]: http://www.goatintheroadproductions.org/works-blog/2014/8/25/numb
[makey]: https://www.makeymakey.com
[kcs]: http://heykyle.co
[config]: https://github.com/darthmall/Dinglake/blob/master/app/config.json