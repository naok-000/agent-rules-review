# agent-rules-review

リポジトリの agent 向け規則（`AGENTS.md`，`CLAUDE.md`，`rules/`，雛形，検査 script）をレビューする skill．

## skill

- [review-agent-rules](skills/review-agent-rules/SKILL.md)：9 つの原則で規則を監査し，欠陥の一覧と修正案を返す．`--fix` で修正まで行う．ユーザが `/review-agent-rules` で呼ぶ．

## 導入（nix）

[agent-skills-nix](https://github.com/Kyure-A/agent-skills-nix) の source として追加する．

```nix
# flake.nix
inputs.agent-rules-review = {
  url = "github:naok-000/agent-rules-review";
  flake = false;
};

# programs.agent-skills.sources
agent-rules-review = {
  input = "agent-rules-review";
  subdir = "skills";
};

# programs.agent-skills.skills
enableAll = [ "agent-rules-review" ];
```
