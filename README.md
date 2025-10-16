

# Z O R A R A - > https://zoraraexecutor.pages.dev

📈 PulseKit

PulseKit is a lightweight, real-time analytics SDK for games and mobile apps. It tracks player events, performance metrics, monetization data, and funnels — all with offline caching and privacy-safe data handling.

✨ Features

⚡ Real-time tracking – low-latency event dispatch

🧩 Cross-platform – Unity, Unreal, Web, Android, iOS

🔒 Privacy-first – GDPR / COPPA compliant, anonymized IDs

📊 Custom events – game-specific metrics or session analytics

🧠 A/B testing – feature toggles, variant tracking, cohort split

💾 Offline queue – auto-resends when network recovers

🌐 REST + WebSocket APIs – integrates with your dashboards

📦 Installation
Unity
https://github.com/yourusername/pulsekit-unity.git

Unreal

Clone to Plugins/PulseKit and enable in Edit → Plugins.

Web / Node.js
npm install pulsekit

🚀 Quick Start (Unity Example)
using PulseKit;
using UnityEngine;

public class AnalyticsDemo : MonoBehaviour
{
    void Start()
    {
        Pulse.Initialize("GAME_ID_123");
        Pulse.Track("session_start");
    }

    void OnApplicationQuit()
    {
        Pulse.Track("session_end");
    }
}

🧩 Custom Events
Pulse.Track("level_complete", new {
    level = 5,
    time = 83.5,
    coins = 320
});


or via REST API:

curl -X POST https://api.pulsekit.dev/events \
  -H "Authorization: Bearer API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"event":"purchase","data":{"item":"sword","price":4.99}}'

📊 Funnels
Pulse.Funnel("onboarding")
     .Step("TutorialStart")
     .Step("TutorialComplete")
     .Step("AccountCreated")
     .Commit();


Then view results in dashboard:

95% → 87% → 81%

🧠 A/B Testing
var variant = Pulse.AB("MenuColorTest", new [] {"blue", "green"});
if (variant == "blue")
    menu.ApplyBlueTheme();
else
    menu.ApplyGreenTheme();
Pulse.Track("menu_color_variant", variant);


Dashboard automatically visualizes conversion per variant.

💾 Offline Handling

All events are stored in local queue when offline:

Pulse.Config.OfflineCache = true;
Pulse.Config.FlushInterval = 30; // seconds

🔐 Privacy & Security

SHA-256 hashed device identifiers

Consent gate integration

Encrypted transport (TLS 1.3)

Optional on-premise server

📊 Web Dashboard

PulseKit Cloud (fictional):

View live sessions, DAU, retention curves

Segment by OS, region, campaign

Export to CSV or BigQuery

open https://dashboard.pulsekit.dev

🧠 Integrations
Platform	Plugin
Unity	✅ Ready
Unreal	✅ Ready
Godot	🔧 In progress
Web	✅ Ready
Mobile SDK	✅ iOS/Android
🛣 Roadmap

Predictive churn models

Cross-game cohort tracking

Revenue attribution

Heatmap visualizer (player movement analytics)

🤝 Contributing

Fork the repo

git checkout -b feat/awesome

Add integration sample or test

Submit a PR 🎉

📜 License

MIT © 2025 PulseKit Contributors
