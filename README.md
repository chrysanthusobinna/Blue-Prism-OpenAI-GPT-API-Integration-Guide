## 🔧 Blue Prism – OpenAI GPT API Integration Guide

### 1. Launch Blue Prism

* Open the **Blue Prism** application.
* Click the **System** tab from the top menu bar.

---

### 2. Set Up API Key as a Credential

1. From the left-hand panel, go to:
   **Security → Credentials**
2. Click **New** on the right-hand pane.
3. Fill in the details:

   * **Name**: `OpenAI API Key`
   * **Description**: `API Key` (optional)
   * **Type**: `Bearer Token`
   * **Value**: Paste your OpenAI API Key (no `Bearer` prefix).
4. Click the **Access Rights** tab:

   * Under **Security Roles**, tick the appropriate roles (e.g., `Developers`, `Web Service Consumers`, or `All Roles`).
   * Optionally, allow access under the **Processes (legacy)** and **Resources (legacy)** tabs.
5. Click **OK** to save.

---

### 3. Add a New Web API Service

1. Under **Objects**, click **Web API Services**.
2. In the right-hand pane, click **Add Service**.
3. In the "Web API: New Web API Service" window:

   * **Name**: `OpenAI API`
   * **Base URL**: `https://api.openai.com/v1`

---

### 4. Configure Common Headers

1. In the left-hand tree, click **Common Headers**.
2. Add the following headers:

   * **Name**: `Authorization`
     **Value**: Leave blank (it will be handled via the credential).
   * **Name**: `Content-Type`
     **Value**: `application/json`

---

### 5. Set Authentication

1. Click **Common Authentication**.
2. Set the values:

   * **Authentication Type**: `Bearer Token`
   * **Credential**: Select `OpenAI API Key`
   * Leave **Expose to process** unchecked
3. Click **OK**.

---

### 6. Add a New Action

1. Under **Actions**, click **Add Action**.
2. Rename the action to something meaningful (e.g., `Completion`).

---

### 7. Set Action Parameters

1. Click on **Parameters** under your action.
2. Add a new parameter:

   * **Name**: `Prompt`
   * **Description**: e.g., `Text input to send to GPT`
   * **Data Type**: `Text`
   * **Initial Value**: Leave blank
   * **Expose**: ✅ Checked
3. Click **OK**.

---

### 8. Set Request Details

1. Click on **Request** under your action.
2. Set the following:

   * **Method**: `POST`
   * **URL Path**: `/chat/completions`
   * **Body Content (Template)**:

```json
{
  "model": "gpt-4-turbo",
  "messages": [
    {
      "role": "system",
      "content": "You are a helpful assistant."
    },
    {
      "role": "user",
      "content": "[Prompt]"
    }
  ]
}
```

---

### 9. Set Response Mapping

1. Click on **Response** under your action.
2. Add a new output parameter:

   * **Parameter**: `content`
   * **Description**: `Content of response`
   * **Data Type**: `Text`
   * **Method**: `Json Path`
   * **Json Path**: `$.choices[0].message.content`
3. (Optional) Click **Check Code** to validate.
4. Click **OK**.

---

## 🧪 Testing the API in Process Studio

### 1. Create a Test Process

1. Go to the **Studio** tab.
2. Right-click **Processes** → Select **Create Process**.
3. Name the process (e.g., `Test OpenAI`) → Click **Next** → **Finish**.
4. Double-click the process to open it.

---

### 2. Add a Data Item

1. Right-click the canvas → **Insert Data**.
2. Set:

   * **Name**: `Prompt`
   * **Type**: `Text`
   * **Initial Value**: `Explain low-code technology`
3. Click **OK**.

---

### 3. Insert an Action Stage

1. Right-click canvas → **Insert Action**.
2. Configure:

   * **Name**: `Call OpenAI`
   * **Business Object**: `Chat gbt Completion API`
   * **Action**: `Completion`
3. Go to **Inputs**:

   * Assign `[Prompt]` to the **Prompt** parameter.
4. Go to **Outputs**:

   * Create a new data item `GPT_Response` and assign it to output `content`.

---

### 4. Link the Flow

* Connect the stages:
  **Start → Call OpenAI → End**

---
 
