# Load necessary libraries
library(ggplot2)
library(reshape2)

# Load the dataset
data <- read.csv("Virulence_Factors.csv")

# Check the column names to identify the issue
colnames(data)

# Assuming the first column is for clinical conditions, let's rename it properly
colnames(data)[1] <- "Clinical_Condition"

# Reshape the data to long format for easy plotting
data_long <- melt(data, id.vars = "Clinical_Condition", 
                  variable.name = "Virulence_Gene", 
                  value.name = "Percentage")

# Plot the data using ggplot2
ggplot(data_long, aes(x = Clinical_Condition, y = Percentage, fill = Virulence_Gene)) +
  geom_bar(stat = "identity", position = "dodge") +
  labs(title = "Percentage of Virulence Genes in Clinical Bacterial Isolates",
       x = "Clinical Condition", 
       y = "Percentage of Virulence Genes") +
  theme_minimal() +
  theme(axis.text.x = element_text(angle = 45, hjust = 1)) +
  scale_fill_brewer(palette = "Set3")
