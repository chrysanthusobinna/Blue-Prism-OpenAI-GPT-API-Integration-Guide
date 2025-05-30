
# 🧠 Import and Use the Blue Prism – OpenAI GPT API Integration Release

If you're looking to integrate OpenAI's GPT API into Blue Prism without building it from scratch, you're in luck! I've packaged a complete, ready-to-use Blue Prism release that includes:

* ✅ A **Web API configuration** for OpenAI's GPT API
* ✅ A **test process** to validate your integration
* ✅ A **Bearer Token credential** to secure your API calls

This guide will walk you through importing, customizing, and running the release.

---

## 📦 What's Inside the Release?

The exported release contains:

* **Process:** `Test OpenAI`
* **Web API Service:** `OpenAI API`
* **Credential:** `OpenAI API Key`
---

## 📥 Step 1: Import the Release

1. Download the prebuilt release file from this repository:
   👉 [**Download Blue Prism – OpenAI GPT API Integration.bprelease**](./Blue%20Prism%20–%20OpenAI%20GPT%20API%20Integration.bprelease)

2. Launch **Blue Prism**.

3. Click the **File** menu in the top-left corner.

4. Select **Import → Release / Skill**.

5. Browse and select the downloaded `.bprelease` file.

6. Click **Next**, review the package contents, and then click **Finish** to complete the import.

✅ Once done, you'll see the imported process, Web API service, and credential under their respective sections.

---

## 🔐 Step 2: Update the API Key

1. Go to **System → Security → Credentials**.
2. Open the credential named **OpenAI API Key**.
3. Replace the existing value with your **actual OpenAI API Key** (don’t include `Bearer` — Blue Prism adds it automatically).
4. Make sure correct roles (e.g., **Developers**) are granted access under **Access Rights**.
5. Click **OK** to save.

---

## ⚙️ Step 3: Customize (Optional)

* You can modify the **Web API** action if you wish to:

  * Change the model from `"gpt-4-turbo"` to `"gpt-3.5-turbo"` or another supported model.
  * Adjust the system prompt from `"You are a helpful assistant."` to something tailored (e.g., `"You are a legal document summarizer."`).

---

## 🧪 Step 4: Run the Test Process

1. Open the imported **Test OpenAI** process from **Studio**.
2. Double-click the **Prompt** data item and set your test prompt (e.g., `"Explain low-code platforms"`).
3. Click **Run** ▶️ and observe the output in the `AI_Response` variable.
4. You can link this process to other workflows or expand it as needed.

---

## 📌 Prerequisites

Before running the integration, ensure:

* You have an active [OpenAI account](https://platform.openai.com/).
* You have sufficient credits or quota:
  🔗 [Check your usage and billing](https://platform.openai.com/account/usage)

---

## 🧠 Summary

This release accelerates your ability to experiment with OpenAI’s capabilities directly from Blue Prism. Whether you're building chatbots, automating document proccessing, or enhancing decisions with generative AI — this setup is your foundation.

---

### 🙋‍♂️ About the Author

**Chrysanthus Obinna Chiagwah**  
Developer \| AI & Automation Enthusiast  
📍 United Kingdom  
🔗 [LinkedIn Profile](https://www.linkedin.com/in/chrysanthus-obinna)  
🌐 [Portfolio Website](https://www.chrys-online.com)  

---
