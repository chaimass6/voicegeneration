🎵 WaveGAN Voice Generation
This project demonstrates audio generation using WaveGAN, a GAN-based model capable of synthesizing raw audio waveforms. Using pretrained checkpoints, this notebook allows you to generate realistic audio samples from various domains including speech, musical instruments, and environmental sounds.

📚 What is WaveGAN?
WaveGAN is a Generative Adversarial Network (GAN) architecture that synthesizes raw audio waveforms. It adapts the DCGAN structure to 1D convolutions for audio generation and can produce coherent and realistic sounds from latent vectors.

🗃️ Datasets Used
The following pretrained datasets are supported and can be selected via the dataset variable:

Dataset	Description	Source
digits	Spoken digits from the SC09 dataset	sc09
speech	TIMIT dataset for general speech synthesis	timit
birds	Environmental sounds of birds chirping	Custom environmental dataset
drums	Percussion instrument sounds (drums)	Custom drums dataset
piano	Piano note audio samples	Custom piano dataset

You can switch between datasets by modifying the dataset variable in the code.

🚀 How It Works
A latent vector z is randomly sampled from a uniform distribution.

This vector is passed through the WaveGAN generator to produce a raw audio waveform.

The waveform is also transformed into a spectrogram for visualization.

Both audio and spectrograms are displayed for analysis.

🧠 Pretrained Models
The project downloads the appropriate .ckpt files for each dataset from the official WaveGAN model releases:

bash
Copy
Edit
# Example for 'digits'
wget https://s3.amazonaws.com/wavegan-v1/models/sc09.ckpt.index
wget https://s3.amazonaws.com/wavegan-v1/models/sc09.ckpt.data-00000-of-00001
wget https://s3.amazonaws.com/wavegan-v1/models/sc09_infer.meta
⚙️ Setup Instructions
Make sure you are using Google Colab or a local environment with TensorFlow 1.x compatibility.

Select your dataset in the code:

python
Copy
Edit
dataset = 'piano'  # Change to: 'digits', 'speech', 'birds', 'drums', or 'piano'
Run the notebook to:

Confirm GPU availability

Download the model files

Load the TensorFlow graph

Generate audio samples

📦 Requirements
Python 3.x

TensorFlow 1.x or TensorFlow 2.x with v1 compatibility (tf.compat.v1)

NumPy

PIL

IPython for audio display

🎧 Sample Outputs
Generated samples include:

Spectrogram of the audio

Playable audio snippet using IPython.display.Audio

🧪 Example Output
python
Copy
Edit
Example 0
[Spectrogram image]
[Playable audio]
💡 Notes
If you're running on TensorFlow 2.x, the code uses tf.compat.v1 for backward compatibility.

GPU acceleration is recommended for faster sample generation.
