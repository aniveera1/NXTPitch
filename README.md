# NXTPitch

## Background
NXTPitch is a continuation project that my partner and I developed at Cal Hacks 2017, which enables students to upload videos/pdf documents and receive feedback regarding how effective the content within that medium is. We present our feedback in three main areas: emotional, professional, and highlighted content. Through this feedback students can better tailor their professional content to capture who they truly are, and get that job at their dream company.

## Dependencies
To run the software first use the requirements.txt file to install all the python packages. You will also need the command line tool ffmpeg, which can be found at their website http://www.ffmpeg.org/. Finally you will need API keys for the various APIS: Microsoft Azure, Watson Developer Cloud, and Eyeris.

## Setup
After collecting all the dependencies, open your directory and copy a video file called "new.mov" into it. This is the video file that the analysis will be performed on. Then run "python run.py", and you can then navigate to http://127.0.0.1:5000/ in your browser to see the feedback.

## Future Steps
Given that this was built at a hackathon, there are several things that I would like to improve on for the next iteration. First there needs to be a more robust structure for deployment to production, since the current version simply leverages Flask's built-in development server for local testing. I believe the simplest approach would be to use container based development, use a production ready server such as Gunicorn, and deploy to either AWS or Heroku. Second the logic needs to be more robust, specifically to handle the various edge cases that arise when dealing with imperfect input associated with video/pdf files. Of the top of my head a few things I would implement are preprocessing of the resume to remove any non-alphanumeric characters, failbacks for situations where the text is unable to be extracted from the resume or the audio from the elevator pitch, and error checking for all API calls. Finally performance could use some help, and specifically I would use threads to enable parallelization of the various API calls. 
