# --- Boxplot: weight distribution grouped by sex ---
plot_weight_by_sex <- ggplot(bigclass, aes(x = sex, y = weight, fill = sex)) +
  geom_boxplot(alpha = 0.8, outlier.colour = "#CC79A7") +
  scale_fill_manual(values = c("F" = "#009E73", "M" = "#0072B2")) +
  labs(
    title = "Weight Distribution by Sex",
    x = "Sex",
    y = "Weight"
  ) +
  theme_minimal() +
  theme(
    plot.background = element_rect(fill = "white", color = NA),
    panel.background = element_rect(fill = "white", color = NA),
    axis.title.x = element_text(size = 18, color = "black"),
    axis.title.y = element_text(size = 18, color = "black"),
    axis.text.x = element_text(size = 14, color = "black"),
    axis.text.y = element_text(size = 14, color = "black"),
    plot.title = element_text(size = 20, face = "bold", hjust = 0.5),
    legend.position = "none"
  )
plotly_weight_by_sex <- ggplotly(plot_weight_by_sex)
htmlwidgets::saveWidget(plotly_weight_by_sex, "media/plots/weight_distribution_by_sex_boxplot.html", selfcontained = TRUE)
