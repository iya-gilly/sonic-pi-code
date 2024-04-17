#this is where all CS code will be posted :)))
use_bpm 140
nature = "C:/Users/aniya_gillings/Downloads/nature.wav"
lol = "C:/Users/aniya_gillings/Downloads/(FREE) PinkPantheress x Pop type beat - BARBIE.mp3"

use_bpm 110
sample  lol
sleep 255
2.times do
  play :eb5
  sleep 0.5
  play :bb4
  sleep 0.5
  play :g4
  sleep 0.5
  play :eb5
  sleep 0.5
  
  play :bb4
  sleep 0.5
  play :g4
  sleep 0.5
  play :eb5
  sleep 0.5
  play :bb4
  sleep 0.5
  
  play :db5
  sleep 0.5
  play :bb4
  sleep 0.5
  play :f4
  sleep 0.5
  play :db5
  sleep 0.5
  
  play :bb4
  sleep 0.5
  play :f4
  sleep 0.5
  play :db5
  sleep 0.5
  play :bb4
  sleep 0.5
  
  play :db5
  sleep 0.5
  play :bb4
  sleep 0.5
  play :f4
  sleep 0.5
  play :db5
  sleep 0.5
  
  play :bb4
  sleep 0.5
  play :f4
  sleep 0.5
  play :db5
  sleep 0.5
  play :bb4
  sleep 0.5
  with_fx :echo do
    sample  nature, amp:5, env_curve:4
  end
  play :c5
  sleep 0.5
  play :ab4
  sleep 0.5
  play :f4
  sleep 0.5
  play :c5
  sleep 0.5
  
  play :ab4
  sleep 0.5
  play :f4
  sleep 0.5
  play :c5
  sleep 0.5
  play :ab4
  sleep 0.5
end
use_bpm 98
with_fx :echo do
  sample :guit_em9
end
sleep 3
def play_legato_note(note_value, duration)
  release_duration = duration
  if duration < 1
    release_duration = 1
  end
  
  play note_value, release: release_duration, amp: 0.65
  sleep duration
end

# arpeggio parts

def arp_d_2
  play_pattern_timed [:d4, :fs4, :b4, :cs5, :fs5, :fs4, :b4, :cs5], [0.5], amp: 0.5
  play_pattern_timed [:e5, :fs4, :b4, :cs5, :fs5, :fs4, :b4, :cs5], [0.5], amp: 0.5
end

def arp_fs_2
  play_pattern_timed [:cs4, :e4, :b4, :cs5, :fs5, :fs4, :b4, :cs5], [0.5], amp: 0.5
  play_pattern_timed [:e5, :fs4, :b4, :cs5, :fs5, :fs4, :b4, :cs5], [0.5], amp: 0.5
end


def bass_d
  play :d2, release: 1.5
  sleep 1.5
  play :d2, release: 1.5
  sleep 1.5
  play :a2
  sleep 0.5
  play :d3
  sleep 0.5
end

def bass_fs_2
  play :fs2, release: 1.5
  sleep 1.5
  play :fs2, release: 1.5
  sleep 1.5
  play :cs3
  sleep 0.5
  play :fs3
  sleep 0.5
  
  play :fs2, release: 1.5
  sleep 1.5
  play :fs2, release: 1.5
  sleep 1.5
  play :e2
  sleep 1
end
def bass_cs_2
  play :cs2, release: 1.5
  sleep 1.5
  play :cs2, release: 1.5
  sleep 1.5
  play :gs2
  sleep 0.5
  play :cs3
  sleep 0.5
  
  play :cs2, release: 1.5
  sleep 1.5
  play :cs2, release: 1.5
  sleep 1.5
  play :gs2
  sleep 1
end

def bass_e
  play :e2, release: 1.5
  sleep 1.5
  play :e2, release: 1.5
  sleep 1.5
  play :b2
  sleep 0.5
  play :e3
  sleep 0.5
end

live_loop :arp do
  arp_d_2
  arp_d_2
  arp_d_2
  arp_fs_2
  
  loop do
    arp_d_2
    arp_fs_2
  end
end

live_loop :bass do
  sleep 16
  
  bass_d
  bass_d
  bass_fs_2
  
  #melody
  bass_d
  bass_d
  bass_cs_2
  
  bass_d
  bass_d
  bass_fs_2
  
  bass_d
  bass_d
  bass_cs_2
  
  bass_d
  bass_e
  bass_fs_2
end

live_loop :kick_drum do
  sleep 16
  loop do
    sample :drum_tom_lo_soft, rate: 0.5
    sleep 0.75
    sample :drum_tom_lo_soft
    sleep 0.75
    sample :drum_tom_lo_soft
    sleep 1
    sample :drum_tom_lo_soft
    sleep 1.5
  end
end

live_loop :snare_drum do
  sleep 16
  loop do
    sleep 1
    sample :drum_tom_hi_soft
    sleep 1
  end
end

live_loop :melody do
  use_synth :prophet
  
  sleep 32
  
  play_legato_note :gs4, 0.75
  play_legato_note :gs4, 0.75
  play_legato_note :fs4, 0.5
  play_legato_note :fs4, 3.5
  
  play_legato_note :fs4, 0.25
  play_legato_note :gs4, 0.25
  play_legato_note :a4, 0.75
  play_legato_note :b4, 0.75
  play_legato_note :a4, 0.25
  play_legato_note :gs4, 0.25
  
  play_legato_note :fs4, 0.75
  play_legato_note :fs4, 0.75
  play_legato_note :e4, 0.5
  play_legato_note :e4, 5.5
  
  play_legato_note :cs4, 0.5
  
  play_legato_note :gs4, 0.75
  play_legato_note :gs4, 0.75
  play_legato_note :fs4, 0.5
  play_legato_note :fs4, 3
  sleep 0.5
  play_legato_note :fs4, 0.5
  play_legato_note :gs4, 0.75
  play_legato_note :a4, 0.75
  play_legato_note :b4, 0.5
  
  play_legato_note :b4, 0.75
  play_legato_note :cs5, 0.75
  play_legato_note :cs5, 3.5
  sleep 0.5
  play_legato_note :cs5, 0.5
  play_legato_note :e5, 0.75
  play_legato_note :cs5, 0.75
  play_legato_note :a4, 5.25
  sleep 0.75
  play_legato_note :a4, 0.5
  play_legato_note :fs4, 1
  play_legato_note :cs5, 1
  
  
  
  play_legato_note :b4, 0.75
  play_legato_note :cs5, 0.75
  play_legato_note :gs4, 1.5
  play_legato_note :fs4, 0.5
  play_legato_note :e4, 3
  sleep 1
  play_legato_note :e4, 0.5
  
  
  play_legato_note :fs4, 0.5
  play_legato_note :a3, 0.5
  play_legato_note :d4, 0.5
  play_legato_note :e4, 0.5
  play_legato_note :fs4, 0.75
  play_legato_note :gs4, 0.75
  play_legato_note :a4, 0.5
  
  play_legato_note :gs4, 0.5
  play_legato_note :b3, 0.5
  play_legato_note :e4, 0.5
  play_legato_note :fs4, 0.5
  play_legato_note :gs4, 0.75
  play_legato_note :a4, 0.75
  play_legato_note :gs4, 0.5
  
  play_legato_note :gs4, 3
  play_legato_note :gs4, 0.5
  play_legato_note :fs4, 0.5
  
  play_legato_note :fs4, 4
  
end
stop

stop
