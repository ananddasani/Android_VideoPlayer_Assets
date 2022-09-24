# Android_VideoPlayer_Assets
Playing Video From Assets and seeking with seek bar

This topic is a part of [My Complete Andorid Course](https://github.com/ananddasani/Android_Apps)

# Code

#### 1st Activity 
```
Button playPauseButton;
SeekBar seekBar;
MediaPlayer mediaPlayer;
SurfaceView surfaceView;

mediaPlayer = MediaPlayer.create(MainActivity.this, R.raw.goku);

surfaceView.setKeepScreenOn(true);

//Create a surface view holder
SurfaceHolder surfaceHolder = surfaceView.getHolder();

        //callback add
        surfaceHolder.addCallback(new SurfaceHolder.Callback() {
            @Override
            public void surfaceCreated(@NonNull SurfaceHolder holder) {
                mediaPlayer.setDisplay(surfaceHolder);
            }

            @Override
            public void surfaceChanged(@NonNull SurfaceHolder holder, int format, int width, int height) {

            }

            @Override
            public void surfaceDestroyed(@NonNull SurfaceHolder holder) {

            }
        });

        //seek Bar working
        seekBar.setMax(mediaPlayer.getDuration());

        seekBar.setOnSeekBarChangeListener(new SeekBar.OnSeekBarChangeListener() {
            @Override
            public void onProgressChanged(SeekBar seekBar, int progress, boolean fromUser) {
                if(fromUser)
                    mediaPlayer.seekTo(progress);
            }

            @Override
            public void onStartTrackingTouch(SeekBar seekBar) {

            }

            @Override
            public void onStopTrackingTouch(SeekBar seekBar) {

            }
        });

        //button working
        playPauseButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                if(mediaPlayer.isPlaying()){
                    playPauseButton.setText("Play");

                    mediaPlayer.pause();
                }
                else {
                    playPauseButton.setText("Pause");

                    mediaPlayer.start();
                }
            }
        });
    }
```

# App Highlight

![Video Player Assets App](https://user-images.githubusercontent.com/74413402/192093107-c11f4fe1-ac2b-40d4-bd3a-1096189f164c.png)
![Video Player Assets Code](https://user-images.githubusercontent.com/74413402/192093112-4aaec9c9-86d4-4bb7-bf56-446da9b3e82f.png)

