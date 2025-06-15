# WhatsApp Chat Analyzer

This project allows you to preprocess and analyze WhatsApp chat data using Python. It provides functionalities to clean the chat data, split the messages by user and date/time, and generate various statistics about chat usage.

## Live Demo
Check out the [WhatsApp Chat Analyzer app](https://abhimanyusingh1413-whatsapp-chat-analyzer-app-svuzap.streamlit.app/) to see a working example.

Live link-
http://abhimanyusingh1413-whatsapp-chat-analyzer-app-svuzap.streamlit.app/

## Features
- Data cleaning using regular expressions  
- Splitting messages into user name and message text  
- Statistics on messages, words, media usage, and more  
- Timeline generation for daily and monthly trends  
- Extracting most common words with stop-word removal  
- Generating WordCloud images for message summaries  

## Requirements
- Python 3.x  
- pandas  
- wordcloud  
- urlextract  
- emoji  

Install these via:
```bash
pip install -r requirements.txt
```

## Usage
1. Export a WhatsApp chat as a text file (`.txt`).  
2. Use the `preprocessor.py` script to parse your text:
   ```python
   from preprocessor import preprocess

   with open('your_chat_file.txt', 'r', encoding='utf-8') as file:
       data = file.read()

   df = preprocess(data)
   ```
3. Use the functions in `helper.py` to generate summaries and statistics:
   ```python
   # Example: Counting total messages
   total_messages = df.shape[0]

   # Example: Getting the top 10 words
   from collections import Counter
   top_words = Counter(" ".join(df['message']).split()).most_common(10)
   ```
4. Visualize data using the `visualization.py` module:
   ```python
   import matplotlib.pyplot as plt
   from visualization import plot_timeline, plot_activity

   # Plot message timeline
   plot_timeline(df)

   # Plot activity pattern
   plot_activity(df)
   ```

## Contributing
Contributions are welcome! Please open an issue or submit a pull request for any enhancements or bug fixes.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

