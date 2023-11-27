# Vision Transformer Image Classifier for the GTSRB (German Traffic Sign Recognition Benchmark) Dataset

## The Critical Challenge of Traffic Sign Recognition
In the realm of autonomous vehicles, the accuracy of traffic sign recognition is paramount. However, current systems often falter under challenging conditions such as occlusions, weather changes, and lighting variations. This is not just a technical problem; it's a safety one. Missed or misclassified signs can compromise the reliability of autonomous vehicles, potentially leading to accidents. By enhancing the robustness of our recognition systems, we can prevent accidents and save lives.

## Why Vision Transformers?
So, why choose Vision Transformers for this task? Unlike traditional Convolutional Neural Networks, Vision Transformers offer state-of-the-art accuracy with greater training efficiency. They excel at global contextual modeling, which is crucial for recognizing partially occluded traffic signs. Their flexible self-attention architecture adeptly handles varying shapes and aspects of traffic signs. Plus, their efficient design is ideal for real-time processing in autonomous vehicles, making them a perfect fit for our project.

<img width="850" alt="ViT Architecture" src="https://github.com/cvetanovskaa/GTSRB-ViT/assets/15224551/1cf81f8a-be60-465f-a450-e70cd4c96adc">

## Model Fine-Tuning Overview ([Model Card](https://huggingface.co/cvetanovskaa/vit-base-patch16-224-in21k-gtsrb-tuned))
- Model Used: Leveradged `google/vit-base-patch16-224-in21k` Vision Transformer model for image classification
- Data Processing: Employed the `ViTImageProcessor` to transform images into a format compatible with the Vision Transformer
- Fine-tuning Details:
  - Dataset: Fine-tuned on the German Traffic Sign Recognition Benchmark (GTSRB), encompassing 43 traffic sign classes, across 39K training and 12K testing images
  - Optimizer: Used an Adam optimizer with a learning rate of 2e-4
  - Training Duration: Model trained for 2 epochs to ensure effective learning without overfitting
- Achieved Performance: Attained an accuracy of 98.7%, showcasing high precision and recall across all classes.

## Demo
Experience this Vision Transformer in action at our Hugging Face Space. This interactive demo allows you to upload traffic sign images and see the model's predictions in real-time. It's a user-friendly way to explore the model's capabilities, providing insights into its accuracy and performance across various traffic sign classes. Test the model with different signs to see how it performs under varying conditions.

https://huggingface.co/spaces/cvetanovskaa/vit-gtsrb-tuned

## Limitations and Critical Analysis

### What has been done:
- Tuned Vision Transformer on specific image classification task
- Capabale of predicting traffic signs with 98% F1-Score
- Created a HuggingFace space to test trained model

### Problems:
- Performance may vary under extreme lighting conditions or when signs are significantly occluded
- Limited to traffic signs that exist in Germany

## Future Work
- Expanding the dataset to include signs from other countries for a more general application
- Integrating the model into a real-time processing system for vehicles
- Exploring the combination of ViT with other models or techniques for enhanced accuracy

## Resources
- Dosovitskiy, A., Beyer, L., Kolesnikov, A., Weissenborn, D., Zhai, X., Unterthiner, T., Dehghani, M., Minderer, M., Heigold, G., Gelly, S., Uszkoreit, J., & Houlsby, N. (2021). An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale. https://doi.org/10.48550/arXiv.2010.11929
- Steiner, A., Kolesnikov, A., Zhai, X., Wightman, R., Uszkoreit, J., & Beyer, L. (2022). How to train your ViT? Data, Augmentation, and Regularization in Vision Transformers. Transactions on Machine Learning Research. https://doi.org/10.48550/arXiv.2106.10270
- "Understanding ADAS: Traffic Sign Recognition." (2021, October 12). Car ADAS Solutions. Retrieved from [(https://caradas.com/understanding-adas-traffic-sign-recognition/#:~:text=Traffic%20Sign%20Recognition%20(TSR)%20is,enter%20signs%2C%20and%20stop%20signs.)https://caradas.com/understanding-adas-traffic-sign-recognition/#:~:text=Traffic%20Sign%20Recognition%20(TSR)%20is,enter%20signs%2C%20and%20stop%20signs.]
- Raw, N. (2022, February 11). Fine-Tune ViT for Image Classification with 🤗 Transformers. Hugging Face. https://huggingface.co/blog/fine-tune-vit
