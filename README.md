# CameraConfigurationOverHeightVehicleDetection
Practitioner's Guide to Camera Configuration for Over-Height Vehicle Detection

%% Extracting Frames from Video
%
% Instructions:
% Step 1) Insert video file
% Step 2) Set the frame extraction rate e.g.  1:frame, for every frame,
%                                             1:5:frame, for every 5th frame etc.
% Step 3) Set the path to save the files.
%%

clc
close all
clear all
Video='insertmovie.avi'; %insert video file here
VideoObject=VideoReader(Video);
frames=VideoObject.NumberofFrames;
for f=1:5:frames % set the frame extraction rate
thisframe=read(VideoObject,f);
figure(1);imagesc(thisframe);title(['Frame ' num2str(f)]); xlabel(['Total number of frames: ' num2str(frames)]);
thisfile=sprintf('C:/Users/insertpathhere/frame_%04d.jpg',f); % Path where files are stored
imwrite(thisframe,thisfile);
end
