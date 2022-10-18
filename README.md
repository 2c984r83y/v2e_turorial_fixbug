# v2e_turorial_fixbug
It is Google colab implemention of https://sites.google.com/view/video2events/home<br> 
You can run the v2e on colab https://colab.research.google.com/drive/1czx-GJnx-UkhFVBbfoACLVZs8cYlcr_M?usp=sharinghon<br>
However the original script above has a bug.<br>
## BUG
```python
# Run command!
!$final_v2e_command
```
It lack of one argument, the input video path.
```
v2e: error: argument -i/--input: expected one argument
```
![image](https://user-images.githubusercontent.com/25505428/196329314-ff9d3910-991e-4028-ad88-3949bbcc0ebf.png)

## Fix bug
add the code below in the upper code block.
```python
video_path = "/content/v2e_tutorial_video.avi"
```
![image](https://user-images.githubusercontent.com/25505428/196329905-764d8514-b18e-4c0b-8c69-5af800fd5061.png)
My final v2e command is
```
v2e -i /content/v2e_tutorial_video.avi -o /content/v2e-output --overwrite --unique_output_folder false --dvs_h5 events.h5 --dvs_aedat2 None --dvs_text None --no_preview --dvs_exposure duration .033 --input_frame_rate 30 --input_slowmotion_factor 1 --disable_slomo --auto_timestamp_resolution false --pos_thres 0.2 --neg_thres 0.2 --sigma_thres 0.03 --cutoff_hz 30 --leak_rate_hz 0.1 --shot_noise_rate_hz 5 --dvs346
```
Then you can generate the output.
![image](https://user-images.githubusercontent.com/25505428/196331424-4f1c88e5-3222-4c0c-8dc6-eb2aab7a14b0.png)
