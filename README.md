🎬 AI-Powered Short Video Generator with Avatar & Captions (n8n Workflow)
This project automates the creation of short-form videos (like Reels or TikToks) using product descriptions. It generates an AI script, image prompts, avatar voiceover, and video with captions—completely hands-free.

🧠 AI Agent Prompt Logic
Your AI agent acts as a scriptwriter and visual planner, performing the following tasks:
Extracts product name + key benefit from a product URL (e.g., Amazon or Shopify).
Writes a 4–6 line persuasive video script in a natural, influencer-style tone.
Generates matching image prompts for each line of the script (DALL·E or similar).
Sends data to Heygen API for avatar generation and voiceover.
Builds video with alternating avatar placement, synced voiceover, and captions.
Outputs the video file.

✨ Output Format (from AI Agent)
json
Copy
Edit
{
  "script": [
    "Hook line to grab attention",
    "Tip 1 - how it works",
    "Tip 2 - benefit",
    "Tip 3 - habit/result",
    "CTA - comment or visit link"
  ],
  "image_prompts": [
    "Prompt for Hook",
    "Prompt for Tip 1",
    "Prompt for Tip 2",
    "Prompt for Tip 3",
    "Prompt for CTA"
  ]
}
⚙️ Modules Overview (What Each Node Does)
Step	Description
📨 Trigger	When chat message received – starts the flow
🧠 AI Agent	Uses Groq/OpenAI model with prompt for script + visuals
🧩 Code	Parses script + prompts
🎭 Avatar	Uses Heygen API to generate avatar voiceover
🖼️ Image Gen	Generates images per script line (looped)
🎞️ Video Creation	Combines avatar and images into a full video
💬 Captions	Optional subtitle overlay
📁 Output	Saves the video file to disk and/or sends webhook

📝 Note: Unlike the Instagram example, this project downloads the final video locally rather than posting it back to Google Sheets.

📥 Input
Product page URL (Amazon / Shopify)

Trigger via chat, webhook, or manual test

📤 Output
A complete, ready-to-post short video

Avatar speaking the script

Background images match the voiceover

Optional subtitles

Video file downloaded locally

🛠️ Stack Used
n8n (workflow builder)

OpenAI or Groq (script + visual planner)

Heygen API (avatar & audio sync)

Image Generation API (DALL·E or custom)

FFmpeg / Command Execution (video assembly, optional subtitles)

Webhook or Disk Node (final output)

📌 To Customize or Extend
🔄 Replace trigger with Google Sheets node for full automation

🌍 Localize scripts to other languages

📲 Auto-upload to TikTok, IG Reels, or YouTube Shorts via API

🧠 Use Pinecone or Simple Memory for smarter responses
