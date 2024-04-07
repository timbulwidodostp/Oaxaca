# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Blinder Oaxaca Decomposition Use Package Oaxaca With (In) R Software
# Install Blinder Oaxaca Decomposition Use Package Oaxaca With (In) R Software
install.packages("readxl")
install.packages("httr")
install.packages("oaxaca")
library("httr")
library("readxl")
library("oaxaca")
# Import Data Excel Into R From Github Olah Data Semarang (timbulwidodostp)
github_link <- "https://github.com/timbulwidodostp/Oaxaca/raw/main/Oaxaca/Oaxaca.xlsx"
temp_file <- tempfile(fileext = ".xlsx")
req <- GET(github_link, 
# authenticate using GITHUB_PAT
authenticate(Sys.getenv("GITHUB_PAT"), ""),
# write result to disk
write_disk(path = temp_file))
Oaxaca <- readxl::read_excel(temp_file)
# Blinder Oaxaca Decomposition Use Package Oaxaca With (In) R Software
oaxaca.results.1 <- oaxaca(ln.real.wage ~ age + female + LTHS + some.college + 
                                          college + advanced.degree | foreign.born, 
                           data = Oaxaca, R = 30)
print(oaxaca.results.1)
# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Finished