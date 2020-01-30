# Audio_Captcha_Project

# Generating captcha files
./generate.py --width 256 --height 64 --length 8 --symbols symbols.txt --count 2000 --output-dir test

This generates 2000 256x64 pixel captchas with 8 symbols per captcha, using the set of symbols in the symbols.txt file. The captchas are stored in the folder
test, which is created if it doesn't exist. The names of the captcha images are scrambled

# Converting audio files to histograms
./audioImageConverter.py --src-dir SourceDirectoryName  --dest-dir TargetDirectoryName

Above Script will convert audio files to Image files containing captcha with 8 character

# Classifying Audio image files to produce output
./audioClassify.py  --model-name audio_model_first_set --captcha-dir ImagesCon --output output.txt --symbols symbols.txt

With --model-name test the classifier script will look for a model called audio_model_first_set.json with weights audio_model_first_set.h5 in the current directory, and load the model
up. The classifier runs all the images in --captcha-dir through the model, and saves the file names and the model's guess at captcha contained in the image in
the --output file.
