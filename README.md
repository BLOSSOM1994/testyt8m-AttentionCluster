# testyt8m-AttentionCluster

فاز 1-پیش پردازش
برای دانلود داده ها 2 راه دارید :
1-	از درایو من دانلود کنید.
https://drive.google.com/drive/folders/1BSdl7flgq5aNGBCh7issM3lHjiIyb-ri?usp=sharing

2-	کد yt8M_tensorflow.ipynb که پیوست شده را اجرا کنید.

مسیر فایل ها در سیستم من به این شکل بوده:
C:\Users\FJ\Downloads\GithubPonisha\yt8m
					|
					|
					|----------\2
					|	--------|frame
					|	|	|-----test
					|		|-----train
					|		|-----val
					|	
					|	
					|	--------|video
					|		|--------test
					|		|--------train
					|		|--------val
					--------|\code
						|
						|-----youtube-9m
							|
							|------train.py

سپس کد و داده ها را به شکلی که در بالا گفته شده پوشه بندی کنید
سپس بر اساس ادرس لپتاپ خودتان ادرس هارو تغییر بدید
پس از تغییر آدرس ها
(شما مسیر های قرمز شده را باید بر اساس سیستم خودتان تغییر دهید و مابقی مسیر ها به همان شکل باقی بمانند.) 

این دستورات را در محیط ترمینال ژوپیتر نوت بوک خودتان وارد کنید به ترتیب ( در عکس  how to run terminal پیوست شده نشان داده شده چگونه ترمینال خود را فعال کنید.)
Windows PowerShell
Copyright (C) Microsoft Corporation. All rights reserved.

Try the new cross-platform PowerShell https://aka.ms/pscore6

1.	PS C:\Users\FJ\Documents> cd ..

2.	PS C:\Users\FJ> cd downloads

3.	PS C:\Users\FJ\downloads> cd GithubPonisha

4.	PS C:\Users\FJ\downloads\GithubPonisha> cd yt8m/code/youtube-8m

در ادامه همان مراحلی که خود گیت هاب انجام داده است را با توجه به مسیر کد خودتان که در شکل بالا گفته شد،انجام دهید:

5.	python train.py --frame_features --model=FrameLevelLogisticModel \ --feature_names='rgb,audio' --feature_sizes='1024,128' \ --train_data_pattern= C:/Users/FJ/downloads/GithubPonisha/yt8m/2/frame/train/train*.tfrecord --train_dir C:/Users/FJ/downloads/GithubPonisha/ yt8m/code/youtube-8m/yt8m/models/frame/sample_model --start_new_model

Evaluate the model by
6.	python eval.py \ --eval_data_pattern C:/Users/FJ/downloads/GithubPonisha/yt8m/2/frame/val/validate*.tfrecord \ --train_dir C:/Users/FJ/downloads/GithubPonisha/ yt8m/code/youtube-8m/yt8m/models/frame/sample_model --segment_labels

7.	python \ inference.py --train_dir C:/Users/FJ/downloads/GithubPonisha/ yt8m/code/youtube-8m/yt8m/models/frame/sample_model \ --output_file C:/Users/FJ/downloads/GithubPonisha/tmp/kaggle_solution.csv \ --input_data_pattern C:/Users/FJ/downloads/GithubPonisha/ yt8m/2/frame/test/test*.tfrecord --segment_labels
