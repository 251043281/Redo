# --- Bar Chart: average Math score by sex ---
plot_math_by_sex <- bigclass %>%
  group_by(sex) %>%
  summarise(avg_math = mean(Math)) %>%
  ggplot(aes(x = sex, y = avg_math, fill = sex)) +
  geom_bar(stat = "identity", alpha = 0.8) +
  scale_fill_manual(values = c("F" = "#D55E00", "M" = "#0072B2")) +
  labs(
    title = "Average Math Score by Sex",
    x = "Sex",
    y = "Average Math Score"
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
plotly_math_by_sex <- ggplotly(plot_math_by_sex)
htmlwidgets::saveWidget(plotly_math_by_sex, "media/plots/math_score_by_sex_barchart.html", selfcontained = TRUE)
