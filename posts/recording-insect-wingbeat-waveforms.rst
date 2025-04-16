.. title: Recording Insect Wingbeat Waveforms
.. slug: recording-insect-wingbeat-waveforms
.. date: 2025-04-11 09:14:51 UTC
.. tags: wingbeat
.. category: 
.. link: 
.. description: 
.. type: text

Updated 2025-04-16

Making the sensor
=================

Coming soon.

Recording signals
=================

Hardware
--------
I record using a USB sound card (`Cable Creation USB Audio External Sound Card <https://www.amazon.com/Adapter-CableCreation-External-Windows-Drivers/dp/B01H2XF8V8?th=1)>`_). 
The sensor is plugged into the microphone jack of the USB device.

Software
--------
I record using a Linux command line program called ``arecord``.
To find the right parameters for the USB sound card, I run the following command which creates a list of installed audio devices.
As you can see, it is recognized as card 2, device 0.

.. code-block:: bash

    $ arecord -l

    List of CAPTURE Hardware Devices
    card 0: PCH [HDA Intel PCH], device 0: ALC1220 Analog [ALC1220 Analog]
    Subdevices: 1/1
    Subdevice #0: subdevice #0
    card 2: Creation [Cable Creation], device 0: USB Audio [USB Audio]
    Subdevices: 1/1
    Subdevice #0: subdevice #0

We can now record a 10 second audio file using the following command.
The parameters are:

* ``-D hw:2,0``: the device to record from (card 2, device 0)
* ``-d 10``: the duration of the recording (10 seconds)
* ``-f dat``: the format of the recording (dat) (16 bit little endian, 48000 Hz)
* ``-c 1``: the number of channels (1 channel, mono)

.. code-block:: bash

    $ arecord -D hw:2,0 -d 10 -f dat -c 1 audio.wav

    Recording WAVE 'audio.wav' : Signed 16 bit Little Endian, Rate 48000 Hz, Mono
