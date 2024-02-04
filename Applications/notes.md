# Applications of TinyML
## 1.4 Machine Learning on Mobile and Edge IoT Devices Part 2

### Quantization
Mapping Float32 to int8, reducing size by  factor of 4 
Post Training quantization is necessary  becasue we want to optimize our models for:
<ul>
    <li>size</li>
    <li>latnecy</li>
    <li>portability</li>
</ul>
the trade-offs are accuracy drops

The tolerability of this accuracy drop is based on application deoplyment use case.
QAT: introduces the measure of accuracy drop and the error by discretizzing the values. The training pipeline can automatically adjust fror this error in the foward pass and backpropgation. 

### TF vs. TFLite
The necessity of the converter

TensorFlow Lite has an increased focus on portability, allowing deployment on different devices and platforms.

### Conversion and Deployment

## 1.5 Keyword Spotting
This is for speech recognition
When you give a machine a command and it 'Awakes" and does something with your next speech to text. Such as "Okay Google" or "Alexa"

Challenges:
<ul>
    <li>Latency and Bandwidth</li>
        <p>Minimize the amount of data sent over the network</p>    
    <li>Accuracy </li>
        <p>Listen continuously</p>
    <li>Personalization</li>
        <p>Triggeer the user and not background noise</p>
    <li>Privacy</li>
        <p>Safeguarding tje secirity </p>
    <li>Battery</li>
        <p></p>
    <li>Memory</li>
        <p></p>
</ul>


### Keyword Spotting Architecture:
![Alt text](image.png)

### KS Datasets:
WHo are the users? Need rich data of audio to train
what do you need? Choosing the rght keyword
What task are you solving? How to interact with ?
How does the real world make this difficult? Background noises need to be accounted for in the dataset and training model

#### Speech Commands: A Dataset for Limited Speech Recognition
Recorded as individual words not sentences
1000-4000 recordings per word
>2,500 volunteers
Recorded with background noise included

TinyMl datasets are much more specific and focussed. THe berevity and size of preexisting datasets are differen tthen what can bne used for TinyML

### Data Collection and Pre-Processing
Sensor Data - 
The wave forms of the audio signal look different and within this signal we must locate the actual word -  THuis is called alignment
Extract critical features. 

Every signal is a composition of different signals. So what we must extract is the signal decomposition.
Fourier (FFt) - What frequencies are present in the signal

Spectograms are created to visualize the signal frequencies.