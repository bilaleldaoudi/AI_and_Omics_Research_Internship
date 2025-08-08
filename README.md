# AI_and_Omics_Research_Internship
dir.create("raw data")
dir.create("script")
dir.create("result")
dir.create("clean data")
dir.create("tasks")
dir.create("plots")
data <- read.csv(file.choose())

#check the classification

class(data$patient_id)
class(data$age)
class(data$gender)
class(data$diagnosis)
class(data$bmi)
class(data$smoker)

#New varaible of smoker

data$smoker_binary <- as.factor(data$smoker)
class(data$smoker_binary)
data$smoker_binary <- ifelse(data$smoker_binary == "Yes",1 ,0)

write.csv(data, file= "clean data/patient_info_clean.csv")
