---
title: Mixer Device Queries
description: Mixer Device Queries
ms.assetid: 3b453802-954b-4356-9ad5-0f8376b6199d
keywords:
- multimedia audio,mixer device queries
- audio,mixer device queries
- audio mixers,device queries
- mixers,device queries
ms.topic: article
ms.date: 05/31/2018
---

# Mixer Device Queries

The mixer services provide functions for determining the number of mixer devices present in the system and the capabilities of the devices. You can also use a mixer services function to determine the device identifier for a mixer device.

You can use the [**mixerGetNumDevs**](https://msdn.microsoft.com/library/Dd757304(v=VS.85).aspx) function to determine how many mixer devices are present in the system. Mixer devices are identified by a device identifier. Device identifiers are determined implicitly from the number of devices present in a given system. They range from zero through one less than the number of devices present.

Before using a mixer device, you must determine its capabilities. Audio capabilities can vary from one multimedia computer to another, so applications need to work with a variety of audio hardware.

You can use the [**mixerGetDevCaps**](https://msdn.microsoft.com/library/Dd757300(v=VS.85).aspx) function to determine the capabilities of mixer devices. This function fills a [**MIXERCAPS**](https://msdn.microsoft.com/library/Dd757291(v=VS.85).aspx) structure with information about the capabilities of a specified device.

The [**mixerGetID**](https://msdn.microsoft.com/library/Dd757301(v=VS.85).aspx) function retrieves the audio mixer device identifier associated with a specified device handle. For example, you could use this function to retrieve the device identifier for an audio mixer and then use the device identifier to adjust the volume or to display another control.

 

 




