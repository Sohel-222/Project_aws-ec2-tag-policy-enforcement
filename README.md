
# EC2 Instance Launch with Enforced Tagging Policy Using AWS Tag Policies

## 📘 Project Description

In this project, we learn how to enforce tagging best practices in AWS by requiring specific tags while launching EC2 instances. This helps with cost control, resource identification, and accountability across the organization.

---

## 🎯 Objective

- Understand AWS tagging best practices.
- Create and apply a tag policy that prevents EC2 instances from being launched without required tags.
- Launch EC2 instance **successfully** with proper tags.
- Attempt to launch EC2 instance **without tags** and verify that it fails.

---

## 🧾 Required Tags

| Tag Key  | Example Value     |
|----------|-------------------|
| Name     | Sohel Shaikh      |
| emailID  | sohel@example.com |
| phoneNo  | 9876543210        |
| Place    | Pune              |

These tags are required at EC2 launch time.

---

## 🛠️ Step-by-Step Instructions

### 🔹 Step 1: Set Up AWS Tag Policy

1. Open AWS Organizations or IAM (if Organizations is not used).
2. Navigate to **Tag Policies**.
3. Create a new Tag Policy JSON like below:

```json
{
  "tags": {
    "Name": {
      "tag_value": {
        "enforced_for": ["ec2:instance"]
      }
    },
    "emailID": {
      "tag_value": {
        "enforced_for": ["ec2:instance"]
      }
    },
    "phoneNo": {
      "tag_value": {
        "enforced_for": ["ec2:instance"]
      }
    },
    "Place": {
      "tag_value": {
        "enforced_for": ["ec2:instance"]
      }
    }
  }
}
```

4. Attach the tag policy to your AWS account.

📷 Screenshot:
![Tag Policy Creation](screenshots/Screenshot%20(106).png)

---

### 🔹 Step 2: Launch EC2 with Tags

1. Go to **EC2 Dashboard** → **Launch Instance**.
2. Fill in details and under the **Tags** section, add all required tags.

📷 Screenshot:
![Launching EC2 with Tags](screenshots/Screenshot%20(110).png)

3. Launch the instance successfully.

📷 Screenshot:
![Successful Launch](screenshots/Screenshot%20(111).png)

---

### 🔹 Step 3: Launch EC2 Without Tags (Expect Failure)

1. Attempt to launch a new EC2 instance but skip the tags.
2. Observe the failure or warning message indicating missing required tags.

📷 Screenshot:
![Failed Launch Without Tags](screenshots/Screenshot%20(112).png)

---

## 🧪 Verification & Results

- ✅ EC2 instance launches successfully **with required tags**.
- ❌ EC2 instance launch **fails or warns** if tags are missing, proving that the tag policy is enforced.

📷 Additional Screenshots:
- ![EC2 Instance Created](screenshots/Screenshot%20(113).png)
- ![Tag Display in EC2 Console](screenshots/Screenshot%20(114).png)

---

## 📄 Report Summary

- **Tag Policy**: Enforces consistent tagging across EC2 resources.
- **Benefit**: Helps with automated billing, auditing, and management.
- **Demonstrated**:
  - Successful launch with tags.
  - Failed launch without tags.
  - Screenshot evidence of both cases.

---

## 📎 Folder Structure

```
Project_Folder/
│
├── README.md
├── report.md / report.pdf
└── screenshots/
    ├── Screenshot (106).png
    ├── Screenshot (109).png
    ├── Screenshot (110).png
    ├── Screenshot (111).png
    ├── Screenshot (112).png
    ├── Screenshot (113).png
    └── Screenshot (114).png
```

---

## 👤 Author

**Sohel Shaikh**  
Email: sohel@example.com  
Location: Pune  
