# AWS_Kiro_CLI

## I am making a AMR dashboard using AWS kiro-cli

```
mkdir Thinley_AMR_Dashborad
cd Thinley_AMR_Dashboard/

```
## Once inside your working directory, you can activate kiro-cli and ask it to plan for you

# kiro-cli keeps on asking for your approval every now and then, which is time consuming and distracting. You can bypass this using. And also kiro asks where you want to index it. So, i am setting it up so that it indexes in the complete working directory
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
Project	What you would build	Difficulty
1. AMR surveillance dashboard	Explore resistance genes by species, sequence type, year and location; display trends, maps and gene combinations
