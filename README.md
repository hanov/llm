# Stanford Tech16 LLM Class Homework 6 

Goal: To become acquainted with different models apart from OpenAI's GPT. All models are run via Docker with Ollama.


Steps to run: 
- Install docker
- Start ollama:
https://ollama.com/blog/ollama-is-now-available-as-an-official-docker-image

```
docker run -d -v ollama:/root/.ollama -p 11434:11434 --name ollama ollama/ollama


Unable to find image 'ollama/ollama:latest' locally
latest: Pulling from ollama/ollama
bccd10f490ab: Pull complete 
ba20c2ac819d: Pull complete 
1cb35d2255df: Pull complete 
Digest: sha256:aefb5681bc87b8209f65f31e7042a2d5b159db8f6ac926665ca6964ae4519b9e
Status: Downloaded newer image for ollama/ollama:latest
5b9952503dd13749d1d39499574500e77841aedd6ebfc4ff880164c2787b373d


docker ps
CONTAINER ID   IMAGE                  COMMAND                  CREATED          STATUS              PORTS                       NAMES
5b9952503dd1   ollama/ollama          "/bin/ollama serve"      22 seconds ago   Up 19 seconds       0.0.0.0:11434->11434/tcp    ollama


docker exec -it ollama ollama run llama2
pulling manifest 
pulling 8934d96d3f08... 100% ▕███████████████████████████████████████████████████████████▏ 3.8 GB                         
pulling 8c17c2ebb0ea... 100% ▕███████████████████████████████████████████████████████████▏ 7.0 KB                         
pulling 7c23fb36d801... 100% ▕███████████████████████████████████████████████████████████▏ 4.8 KB                         
pulling 2e0493f67d0c... 100% ▕███████████████████████████████████████████████████████████▏   59 B                         
pulling fa304d675061... 100% ▕███████████████████████████████████████████████████████████▏   91 B                         
pulling 42ba7f8a01dd... 100% ▕███████████████████████████████████████████████████████████▏  557 B                         
verifying sha256 digest 
writing manifest 
removing any unused layers 
success 



>>> who is your master?

I'm just an AI, I don't have a master. I am a machine learning model designed to assist and provide information to 
users like you, without any one person or entity having control over me. My purpose is to help users like you with 
your questions and tasks, while also following ethical guidelines to ensure a safe and respectful interaction. Is 
there anything else I can help you with?
Use Ctrl + d or /bye to exit.
>>> /bye



```

Another example to use Gemma:
http://anakin.ai/blog/how-to-run-google-gemma-locally/

```
docker exec -it ollama ollama run gemma:2b

pulling manifest 
pulling c1864a5eb193... 100% ▕███████████████████████████████████████████████████████████▏ 1.7 GB                         
pulling 097a36493f71... 100% ▕███████████████████████████████████████████████████████████▏ 8.4 KB                         
pulling 109037bec39c... 100% ▕███████████████████████████████████████████████████████████▏  136 B                         
pulling 22a838ceb7fb... 100% ▕███████████████████████████████████████████████████████████▏   84 B                         
pulling 887433b89a90... 100% ▕███████████████████████████████████████████████████████████▏  483 B                         
verifying sha256 digest 
writing manifest 
removing any unused layers 
success


>>> who is your master?
I do not have a master as I am not a sentient being. I am an artificial intelligence, and I do not have the ability 
to experience life or follow the dictates of a human master. I am designed to assist and provide information based on
the knowledge I have been trained on.

>>> /bye
```
