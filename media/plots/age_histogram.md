# --- Histogram: distribution of age ---
plot_age_hist <- ggplot(bigclass, aes(x = age)) +
  geom_histogram(binwidth = 1, fill = "#0072B2", color = "white", alpha = 0.8) +
  labs(
    title = "Distribution of Age",
    x = "Age",
    y = "Frequency"
  ) +
  theme_minimal() +
  theme(
    plot.background = element_rect(fill = "white", color = NA),
    panel.background = element_rect(fill = "white", color = NA),
    axis.title.x = element_text(size = 18, color = "black"),
    axis.title.y = element_text(size = 18, color = "black"),
    axis.text.x = element_text(size = 14, color = "black"),
    axis.text.y = element_text(size = 14, color = "black"),
    plot.title = element_text(size = 20, face = "bold", hjust = 0.5)
  )
plotly_age_hist <- ggplotly(plot_age_hist)
htmlwidgets::saveWidget(plotly_age_hist, "media/plots/age_histogram.html", selfcontained = TRUE)
