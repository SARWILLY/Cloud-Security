# 🔍 Security Monitoring with CloudTrail and SNS

---

## 🧭 Monitoring Root Account Usage

One of the most critical security measures I’ve implemented is tracking activity from the **root user** in AWS. Since the root account has unrestricted access, I wanted real-time alerts anytime it was used.

### 🛠️ My Setup

1. **Enabled CloudTrail logging** for all management events—both read and write.
2. **Created a CloudWatch metric filter** to detect root activity:
   ```json
   { $.userIdentity.type = "Root" && $.userIdentity.invokedBy NOT EXISTS }
   ```
   - Connected the filter to an SNS Topic that sends email notifications.
- Subscribed my email to the topic for instant alerts.
- Tested the setup by logging in with the root user and viewing billing—an alert landed in my inbox as expected.
- 
📸 Screenshot:
  ![Root Activity DetectedSNS alert triggered by root account](docs/docs/screenshots/screenshot-1753275813773.png)

### ✅ Why This Matters to Me
- I rarely use the root account, and I treat it like a red flag if it's ever activated.
- This alerting setup gives me immediate visibility and lets me take action fast if something unexpected happens.
- It’s a simple yet powerful step in building secure habits while working with cloud services.
