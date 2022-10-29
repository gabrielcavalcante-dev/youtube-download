# youtube-download

abra seu terminal e instale a biblioteca pytube

      pip install pytube
       
algoritmo para fazer o download do vídeo

      #importe a biblioteca
      from pytube import YouTube

      #link de entrada
      link = input("Cole o link para iniciar o download: ")
      yt = YouTube(link)

      #Informações sobre o vídeo
      result = {
          "Titulo": yt.title,
          "Tamanho do vídeo": yt.length,
          "Número de views": yt.views,
          "Avaliação de vídeo": yt.rating
      }
      print(result)

      #busca a melhor resolução para o vídeo
      ys = yt.streams.get_highest_resolution()
      print("Baixando...")

      #executa o download
      ys.download()
      print("Download concluído")
