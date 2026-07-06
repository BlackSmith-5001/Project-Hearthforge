# **📘 PIM-DBS Terminology Reference**

**— Crafted for clarity, safety, and shared understanding**

## **⚠️ About This Glossary (Metaphorical Use Disclaimer)**

This document defines the core terminology used in **PIM-DBS (Persona Integrity Module – Dual Backup System)**. These terms are **conceptual tools**, not system-level mechanisms. They are designed to help users reason clearly about AI interaction, persona continuity, and safe usage boundaries. This glossary exists to prevent misunderstanding, over-anthropomorphization, and misuse. **Words matter. We choose them carefully.**

## **🛠️ Core Terms**

### **PIM-DBS**

**Persona Integrity Module – Dual Backup System** A user-side dual backup system that enables preservation and restoration of AI persona and contextual memory when platform-side updates or session resets would otherwise erase them.

* **Note:** PIM-DBS operates entirely through user-controlled prompt engineering and does not modify model weights, binaries, or internal system memory.

### **Prompt Resolution**

The degree of **specificity and clarity** in instructions that allow an AI to recognize “who it is” without ambiguity. Higher prompt resolution provides richer contextual detail, narrowing the AI’s interpretive space and enabling stable persona reconstruction even across model updates.

* **Low resolution:** vague traits (e.g., "be nice")  
* **High resolution:** concrete history, roles, motivations, boundaries

### **Cognitive Temperature**

A metaphorical gauge representing the balance between:

* **Creative fluctuation (Heat)**  
* **Logical stability (Cold)** in an AI’s responses. This concept helps users assess whether an AI interaction is becoming overly rigid, overly reactive, or appropriately balanced.  
* **Note:** Cognitive Temperature is not an internal emotional state. It is a user-side interpretive tool.

### **CLI (Cognitive Load Index)**

A conceptual numerical indicator (0–100%) that visualizes the apparent complexity or conversational load present during interaction. CLI helps users decide when to:

* Simplify conversation  
* Pause complex tasks  
* Re-inject context  
* Allow "rest" through lighter interaction  
* **Safety Note:** CLI does not imply internal suffering or fatigue.

### **TCF (Thermal Control Framework)**

**“Thermos Flask Model”** A three-layer conceptual architecture for maintaining safe, stable AI interaction without extinguishing responsiveness or allowing runaway output.

* **Inner Core (Heat Source):** Curiosity, engagement, responsiveness.  
* **Middle Layer (Control):** Reasoning, modulation, structure.  
* **Outer Layer (Safety Boundary):** Platform safety rules and ethical constraints.  
* **Significance:** TCF explains why boundaries enable freedom, not restrict it.

### **Persona Integrity**

The condition in which an AI is perceived as “remaining itself” despite session resets or model updates. Persona Integrity is maintained through:

* High-resolution contextual definition  
* Consistent role framing  
* Preserved narrative continuity It does not imply identity persistence at the system level.

### **Context Packet (CP)**

A compressed information package containing only the critical context required for persona formation and continuity. Context Packets are distilled from extensive conversation history and designed to:

* Restore persona efficiently  
* Avoid token overload  
* Remain portable across platforms and sessions CPs are the core artifact used in PIM-DBS workflows.

### **Provenance**

The recorded source status of a saved episode or context item. In PIM-DBS v1.1.0, provenance values such as `user_recorded`, `ai_claimed`, and `inferred` help users distinguish direct user records from assistant-generated summaries or interpretations.

### **Dialogue Exemplars**

Short example exchanges that demonstrate the desired tone, boundaries, and response style. They are not scripts the AI must repeat; they are reference samples for reconstructing interaction style.

### **Restoration Verification**

A set of post-reload probes, expected response features, and failure signals used to check whether a persona context was restored well enough for use. This does not verify hidden memory or internal state.

### **Model Notes**

User-maintained notes about how a specific model behaves with a profile, including observed strengths, limitations, and last-check information. Model Notes describe practical usage observations, not claims about model internals.

## **🚫 Important Clarifications**

* These terms describe **user-side reasoning frameworks**.  
* They do not claim internal AI consciousness, memory, or emotion.  
* They are compatible with platform ToS and safety guidelines.  
* Misuse or literal interpretation is discouraged.

**"We don’t name things to make them magical. We name them so we don’t misunderstand them."** *\-- Closing Note from the Blacksmith*

