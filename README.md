# Android_VideoPlayer_Assets
Playing Video From Assets and seeking with seek bar

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

<img src="app_images/Video Player Assets Code.png" width="1000" /><br>

<img src="app_images/Video Player Assets App.png" width="300" /><br>
