# Visit https://github.com/lowlighter/metrics#-documentation for full reference
name: Metrics
on:
  # Schedule updates (each hour)
  schedule: [{cron: "0 * * * *"}]
  # Lines below let you run workflow manually and on each commit
  workflow_dispatch:
  push: {branches: ["master", "main"]}
jobs:
  github-metrics:
    runs-on: ubuntu-latest
    permissions:
      contents: write
    steps:
      - uses: lowlighter/metrics@latest
        with:
          # Your GitHub token
          # The following scopes are required:
          #  - public_access (default scope)
          # The following additional scopes may be required:
          #  - read:org      (for organization related metrics)
          #  - read:user     (for user related data)
          #  - read:packages (for some packages related data)
          #  - repo          (optional, if you want to include private repositories)
          token: ${{ secrets.METRICS_TOKEN }}

          # Options
          user: RickDas32k
          template: classic
          base: header, activity, community, repositories, metadata
          config_timezone: Asia/Calcutta
          plugin_achievements: yes
          plugin_achievements_display: detailed
          plugin_achievements_secrets: yes
          plugin_achievements_threshold: C
          plugin_calendar: yes
          plugin_calendar_limit: 1
          plugin_followup: yes
          plugin_followup_archived: yes
          plugin_followup_sections: repositories
          plugin_habits: yes
          plugin_habits_charts: yes
          plugin_habits_charts_type: classic
          plugin_habits_days: 14
          plugin_habits_facts: yes
          plugin_habits_from: 200
          plugin_habits_languages_limit: 8
          plugin_habits_languages_threshold: 0%
          plugin_habits_trim: yes
          plugin_isocalendar: yes
          plugin_isocalendar_duration: half-year
          plugin_repositories: yes
          plugin_repositories_featured: NikAmore, GANITADDA
          plugin_repositories_order: featured, pinned, starred, random
          plugin_repositories_pinned: 2
          plugin_screenshot: yes
          plugin_screenshot_background: yes
          plugin_screenshot_mode: image
          plugin_screenshot_selector: body
          plugin_screenshot_title: Screenshot
          plugin_screenshot_url: https://portfolio-eight-xi-sdc4fsdxek.vercel.app/
          plugin_screenshot_viewport: {
  "width": 1280,
  "height": 1280
}
