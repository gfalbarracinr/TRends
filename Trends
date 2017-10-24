#libraries
library(wordcloud)
library(twitteR)
library(tm)
library(extrafont)
font_import()


#Functions


#set up
consumer_key <- 'your consumer_key'
consumer_secret <- 'your consumer_secret'
access_token <- 'your access_token'
access_secret <- 'your access_secret'


setup_twitter_oauth(consumer_key, consumer_secret, access_token, access_secret)




#main code
location <- 368148
#location <- readlines("Type a location to get trends")
trends <-getTrends(location)

#print(trends)

tw_corpus <- Corpus(VectorSource(trends$name))

#clean_words<-clean_words[-grep("http|@|#|ü|ä|ö", clean_words)]
#clean_words<-clean_words[-grep("search", clean_words)]

wordcloud(tw_corpus, min.freq=1,width=12,height=8, res=300)

#### playing with the settings 

wordcloud(tw_corpus, min.freq=1, vfont=c("serif", "plain"),width=12, height=8,res=300)
wordcloud(tw_corpus, min.freq=1, vfont=c("script", "plain"),width=12, height=8,res=300)
wordcloud(tw_corpus, min.freq=1, vfont=c("gothic italian", "plain"), width=12,height=8, res=300)


pal<-brewer.pal(7, "Pastel1")
par(bg="darkgray")
wordcloud(tw_corpus, min.freq=1, vfont=c("script", "plain"), colors=pal, width=12,height=8, res=300)

#### feature image

pal<-brewer.pal(7, "Dark2")
par(bg="lightgray")
wordcloud(tw_corpus, min.freq=1, vfont=c("script", "plain"), colors=pal, width=12,height=8, res=300)



#df <- data.frame(text=unlist(sapply(tw_corpus, '[', "content")), stringAsFactors=F)
write.csv(trends, file="trendTweets.csv")


