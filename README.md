freqdict <- read_tsv("https://github.com/agricolamz/DS_for_DH/raw/master/data/freq_dict_2011.csv")

## Parsed with column specification:
## cols(
##   lemma = col_character(),
##   pos = col_character(),
##   freq_ipm = col_double()
## )

freqdict %>% 
  arrange(desc(freq_ipm)) %>% 
  mutate(id = 1:n()) %>% 
  slice(1:150) %>% 
  ggplot(aes(id, freq_ipm))+
  geom_point()
