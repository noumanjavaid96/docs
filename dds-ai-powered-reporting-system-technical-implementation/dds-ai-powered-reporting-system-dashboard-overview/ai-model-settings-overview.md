# AI Model Settings Overview

{% hint style="info" %}
## <mark style="color:orange;">Again</mark> <mark style="color:orange;"></mark><mark style="color:orange;">**Please note that this page is not part of the MVP. It will be included in the final product as part of the comprehensive AI Management Reporting System.**</mark>
{% endhint %}

This document explains the AI Model Settings page within the DDS AI-powered reporting system. This page allows administrators to configure the AI model used for report generation at either a global (system-wide) or individual store level. The settings control aspects like model selection, output length, response creativity, and content filtering.

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

#### 1. Settings Scope

* **Purpose:** Define the scope of the applied AI model settings.
* **Options:**
  * **Global Settings:** Apply the settings to all dealerships in the DDS system.
  * **Individual Store Settings:** Configure settings for a specific dealership (selected from a dropdown, not visible in the image).

#### 2. Model Configuration

This section allows fine-tuning of the AI model's behavior:

* **AI Model:**
  * **Purpose:** Choose the AI model to be used for report generation.
  * **Selection:** A dropdown menu (not fully expanded in the image) provides a list of available AI models. The current selection is "GPT-4."
* **Temperature:**
  * **Purpose:** Controls the randomness or "creativity" of the AI model's output. Higher temperatures result in more diverse and unpredictable responses, while lower temperatures produce more focused and deterministic outputs.
  * **Current Value:** 0.7 (set using a slider control).
* **Max Tokens:**
  * **Purpose:** Sets the maximum number of tokens (roughly proportional to words) that the AI model will generate in its response.
  * **Current Value:** 2048 (adjustable using a slider).
* **Top P:**
  * **Purpose:** A parameter that influences the range of words the AI model considers during text generation. A lower Top P value results in more focused and predictable outputs, while a higher value allows for a wider range of word choices.
  * **Current Value:** 1 (adjustable using a slider).
* **Frequency Penalty:**
  * **Purpose:** Discourages the AI model from repeating the same phrases or words too frequently. Higher penalties make the output more varied.
  * **Current Value:** 0 (adjustable using a slider).
* **Presence Penalty:**
  * **Purpose:** Penalizes the model for introducing new topics or concepts that are not present in the prompt. Higher penalties keep the response more focused on the original request.
  * **Current Value:** 0 (adjustable using a slider).

#### 3. Content Filtering

* **Purpose:** Control whether or not to enable content filtering for AI-generated reports.
* **Option:**
  * **Enable content filtering:** This will likely activate filters to prevent the AI model from generating inappropriate or offensive content.

#### 4. Database Synchronization

* **Purpose:** Sync the AI model with the latest data from the dealership database.
* **Last Sync Time:** Displays the date and time of the last successful database synchronization (2023-08-25 14:30:00 in the example).
* **Action:**
  * **Sync Database:** A button that triggers the synchronization process to update the AI model with the most recent data.

