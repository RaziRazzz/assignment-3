
library(ggplot2)
library(plotly)
library(htmlwidgets)

# Assuming X007..1. is available in the R environment
df_machine1 <- X007..1.[X007..1.$Machine == 1,]

p <- ggplot(df_machine1, aes(x = factor(Temperature), y = PartResistance, fill = factor(Pressure))) +
  geom_boxplot() +
  labs(
    title = "Part Resistance by Temperature and Pressure for Machine 1",
    x = "Temperature",
    y = "Part Resistance",
    fill = "Pressure"
  ) +
  theme_minimal() +
  theme(
    axis.title.x = element_text(size = 18),
    axis.title.y = element_text(size = 18),
    axis.text = element_text(size = 14),
    panel.background = element_rect(fill = "white", colour = NA)
  ) +
  scale_fill_manual(values = c("#0072B2", "#D55E00", "#009E73"))

ggplotly_plot <- ggplotly(p)
saveWidget(ggplotly_plot, file = "media/plots/boxplot_resistance_machine1.html", selfcontained = TRUE)

