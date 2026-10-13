# AWS_Kiro_CLI

## I am making a AMR dashboard using AWS kiro-cli

```
mkdir Thinley_AMR_Dashborad
cd Thinley_AMR_Dashboard/

```
## Once inside your working directory, you can activate kiro-cli and ask it to plan for you
kiro-cli keeps on asking for your approval every now and then, which is time consuming and distracting. You can bypass this using. And also kiro asks where you want to index it. So, i am setting it up so that it indexes in the complete working directory
```
mkdir -p .kiro/agents && cat > .kiro/agents/default.json << 'EOF'
  {"allowedTools": ["@builtin"],
    "resources": [
      {"type": "knowledgeBase",
        "source": "file://.",
        "name": "full-project",
        "include": ["**/*"],
        "exclude": ["node_modules/**", ".git/**", "*.log", "__pycache__/**", "*.pyc"],
        "autoUpdate": true}]}
EOF
```
```
kiro-cli chat --trust-all-tools

```

```
/plan
```
Lets say my project is to build a AMR surveillance dashboard to	Explore resistance genes by species, sequence type, year and location; display trends, maps and gene combinations. Ask kiro-cli to do the following

```
Please create a Kiro steering file for this project at .kiro/steering/project-rules.md.
Start the file with front matter that sets inclusion to always.
Add these rules:

## Data
Use simulated data for initial development and label it clearly.
Use one unique isolate ID to link sample metadata and resistance genes.
Support multiple resistance genes per isolate.
Include species, sequence type, collection date, country, region, sampling location and resistance gene.
Treat sequence types as species-specific: ST2 in one species is different from ST2 in another species.
Preserve unknown values and display them as "Unknown".
Show summary cards for isolate count, species count and gene count.
Show yearly isolate counts and resistance gene prevalence trends.
 
# Design
Use readable labels and an accessible, colour-blind-friendly palette.
Keep colours consistent across visualisations.
Include chart titles, axis labels, legends and informative tooltips.
Clearly state whether each chart shows counts or percentages.
Make the dashboard usable on desktop and mobile screens.
  
## Development
Keep data loading, validation, analysis and visualisation code separate.
Document the input schema and provide a small example dataset.
Verify unique-isolate counting, prevalence denominators and filters.
Never place AWS credentials or other secrets in source code.


```
