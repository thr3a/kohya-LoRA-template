# new
accelerate launch --num_cpu_threads_per_process 8 train_network.py --config_file /disk1/train/kotaro/config.toml --dataset_config /disk1/train/kotaro/kotaro.toml

# 透過を白背景にする　& トリミング
for f in *.png; do convert "$f" -background "rgb(255,255,255)" -alpha remove -alpha off -crop 700x+300+0 +repage "../resized/$f"; done

python /disk1/kohya-scripts/tools/resize_images_to_resolution.py --max_resolution 512x512 --save_as_png --interpolation lanczos4 --copy_associated_files '/disk1/train/kotaro/resized' '/disk1/train/kotaro/train'
