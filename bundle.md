---
bundle:
  name: sage
  version: 2.2.0
  description: Strategic advisor for architecture, design, product, and outcome-focused decisions

includes:
  - bundle: git+https://github.com/microsoft/amplifier-foundation@main

tools:
  - module: tool-sage
    source: git+https://github.com/michaeljabbour/amplifier-module-tool-sage@main
    config:
      default_provider: gemini
      default_model: gemini-2.0-flash
      max_tokens: 4096

  - module: tool-rlm
    source: file:///Users/michaeljabbour/dev/amplifier-module-tool-rlm
    config:
      max_recursion_depth: 3
      max_llm_calls: 50
      default_provider: gemini

agents:
  include:
    - sage:agents/sage-consultant.md

context:
  include:
    - sage:context/sage-instructions.md
---

# Sage Strategic Advisor

@sage:context/sage-instructions.md

---

@foundation:context/shared/common-system-base.md
