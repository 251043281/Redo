# --- Scatterplot: height vs weight, coloured by sex ---
plot_height_weight_sex <- ggplot(bigclass, aes(x = height, y = weight, color = sex)) +
  geom_point(size = 3, alpha = 0.8) +
  scale_color_manual(values = c("F" = "#CC79A7", "M" = "#0072B2")) +
  labs(
    title = "Height vs. Weight by Sex",
    x = "Height",
    y = "Weight",
    color = "Sex"
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
    legend.text = element_text(size = 14),
    legend.title = element_text(size = 16, face = "bold")
  )
plotly_height_weight_sex <- ggplotly(plot_height_weight_sex)
htmlwidgets::saveWidget(plotly_height_weight_sex, "media/plots/height_weight_scatterplot.html", selfcontained = TRUE)
