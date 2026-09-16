audio:
  backing_track: "audio/track1.mp3"

  duck_volume: 0.20
  normal_volume: 1.00

tracks:
  2: "audio/track2.mp3"
  3: "audio/track3.mp3"
  4: "audio/track4.mp3"
  5: "audio/track5.mp3"
  6: "audio/track6.mp3"
  7: "audio/track7.mp3"
  8: "audio/track8.mp3"
  9: "audio/track9.mp3"

relay:
  smoke_channel: 1
  smoke_duration: 20

esp32:
  controller1:
    enabled: false
    duration: 30

  controller2:
    enabled: false
    duration: 60

  controller3:
    enabled: false
    duration: 300

state:
  state_file: "state/journey_state.json"

beacons:

  outbound:

    1:
      action: start_backing

    2:
      action: play_track
      track: 2

    3:
      action: play_track
      track: 3

    4:
      action: play_track
      track: 4
      esp32:
        - controller1
        - controller2

    5:
      action: play_track
      track: 5
      esp32:
        - controller3

    6:
      action: pause_backing

    7:
      action: resume_backing

    8:
      action: play_track
      track: 6

    9:
      action: pause_backing

    10:
      action: play_track
      track: 7

    11:
      action: smoke

  return:

    12:
      action: play_track
      track: 8

    13:
      action: play_track
      track: 9

    14:
      action: end_experience
# dudley-canal-show-controller