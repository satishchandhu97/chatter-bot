ChatterBot: Machine learning in Python
ChatterBot
ChatterBot is a machine-learning based conversational dialog engine build in Python which makes it possible to generate responses based on collections of known conversations. The language independent design of ChatterBot allows it to be trained to speak any language.

Package Version Python 3.6 Django 2.0 Requirements Status Build Status Documentation Status Coverage Status Code Climate Join the chat at https://gitter.im/chatterbot/Lobby

An example of typical input would be something like this:

user: Good morning! How are you doing?
bot: I am doing very well, thank you for asking.
user: You're welcome.
bot: Do you like hats?

How it works
An untrained instance of ChatterBot starts off with no knowledge of how to communicate. Each time a user enters a statement, the library saves the text that they entered and the text that the statement was in response to. As ChatterBot receives more input the number of responses that it can reply and the accuracy of each response in relation to the input statement increase. The program selects the closest matching response by searching for the closest matching known statement that matches the input, it then returns the most likely response to that statement based on how frequently each response is issued by the people the bot communicates with.

Installation
This package can be installed from PyPi by running:

pip install chatterbot
Basic Usage
from chatterbot import ChatBot
from chatterbot.trainers import ChatterBotCorpusTrainer

chatbot = ChatBot('Ron Obvious')

# Create a new trainer for the chatbot
trainer = ChatterBotCorpusTrainer(chatbot)

# Train the chatbot based on the english corpus
trainer.train("chatterbot.corpus.english")

# Get a response to an input statement
chatbot.get_response("Hello, how are you today?")
Training data
ChatterBot comes with a data utility module that can be used to train chat bots. At the moment there is training data for over a dozen languages in this module. Contributions of additional training data or training data in other languages would be greatly appreciated. Take a look at the data files in the chatterbot-corpus package if you are interested in contributing.

from chatterbot.trainers import ChatterBotCorpusTrainer

# Create a new trainer for the chatbot
trainer = ChatterBotCorpusTrainer(chatbot)

# Train based on the english corpus
trainer.train("chatterbot.corpus.english")

# Train based on english greetings corpus
trainer.train("chatterbot.corpus.english.greetings")

# Train based on the english conversations corpus
trainer.train("chatterbot.corpus.english.conversations")
Corpus contributions are welcome! Please make a pull request.

Documentation
View the documentation for ChatterBot on Read the Docs.

To build the documentation yourself using Sphinx, run:

sphinx-build -b html docs/ build/
Examples
For examples, see the examples directory in this project's git repository.

There is also an example Django project using ChatterBot, as well as an example Flask project using ChatterBot.

History
See release notes for changes https://github.com/gunthercox/ChatterBot/releases

Development pattern for contributors
Create a fork of the main ChatterBot repository on GitHub.
Make your changes in a branch named something different from master, e.g. create a new branch my-pull-request.
Create a pull request.
Please follow the Python style guide for PEP-8.
Use the projects built-in automated testing. to help make sure that your contribution is free from errors.
License
ChatterBot is licensed under the BSD 3-clause license.
