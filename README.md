# kohya-LoRA-template

[kohya-ss/sd-scripts](https://github.com/kohya-ss/sd-scripts)によるLoRAモデルの作成テンプレートとチュートリアル

### 必ず変更すべき箇所

- config.toml
  - pretrained_model_name_or_path # 学習に使うモデル
  - output_dir # モデルの出力先
- dataset.toml
  - image_dir #　学習画像があるディレクトリの絶対パス

### 実行コマンド例

```
cd /disk1/kohya-scripts
accelerate launch train_network.py --config_file /disk1/train/kohya-LoRA-template/config.toml --dataset_config /disk1/train/kohya-LoRA-template/dataset.toml
```



# new

python /disk1/kohya-scripts/tools/resize_images_to_resolution.py --max_resolution 512x512 --save_as_png --interpolation lanczos4 --copy_associated_files '/disk1/train/kohya-LoRA-template/orig' '/disk1/train/kohya-LoRA-template/train'
