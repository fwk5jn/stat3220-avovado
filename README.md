# stat3220-avovado
examines regional avocado prices

         '''

          avocado<-read.csv("avocado.csv")
          avocadosummary<-avocado[,c(3,4,5,9)]
          summary(avocadosummary)

          library(ggplot2)

          ggplot(avocado, aes(x=type, y=AveragePrice)) + geom_boxplot() + facet_grid(.~year) +
            ggtitle("Average Price ($) of Avocados by Year") +
            theme(plot.title = element_text(hjust = 0.5))

          ggplot(avocado, aes(x=region, y=AveragePrice)) + geom_boxplot(outlier.color="blue") + 
            stat_summary(fun.y="mean", geom="point",colour="red", shape=4) + 
            theme(axis.text.x=element_text(angle=90, hjust=1)) +
            ggtitle("Average Price ($) of Avocados by Region") +
            theme(plot.title = element_text(hjust = 0.5))

          #https://www.kaggle.com/neuromusic/avocado-prices
          #https://www.kiplinger.com/tool/real-estate/T010-S003-home-prices-in-100-top-u-s-metro-areas/index.php
          #https://stackoverflow.com/questions/1330989/rotating-and-spacing-axis-labels-in-ggplot2
          #https://stackoverflow.com/questions/40675778/center-plot-title-in-ggplot2
        '''
