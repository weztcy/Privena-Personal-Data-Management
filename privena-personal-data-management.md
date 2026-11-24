# Portfolio Project Data — Privena - Personal Data Management

- **Category:** `desktop-mobile` (`Mobile App` / `Desktop App` / `Cross-Platform App`)
- **Category Label:** `Mobile App`
- **Accent Color:** `amber`
- **Target Assets Folder:** `public/images/projects/privena_personal_data_management/`
- **Required Local Images:** `banner.webp`, `image01.webp` .. `image02.webp`

## TypeScript Data (`ProjectCaseStudy`)

```typescript
{
  "id": "privena-personal-data-management",
  "code": "PRO-08 // APP-04",
  "title": "Privena - Personal Data Management",
  "category": "desktop-mobile",
  "categoryLabel": "Mobile App",
  "year": "2022",
  "status": "Completed",
  "accentColor": "amber",
  "repoUrl": "https://github.com/weztcy/Privena-Personal-Data-Management",
  "license": "MIT License",
  "banner": "/images/projects/privena_personal_data_management/banner.webp",
  "summary": "Native Android personal data vault combining Firebase Authentication with local Realm note storage and dark-mode Material UI.",
  "projectDescription": "Privena is a native Android application built with Java, Realm, and Firebase to help users organize sensitive personal notes and credentials behind authenticated access. It pairs cloud-backed account registration and password recovery with fast, offline-capable local note storage.",
  "architectureSummary": "Android multi-Activity client connecting Firebase Authentication and Realtime Database for user identity with an embedded Realm object database for reactive local note CRUD operations.",
  "techStack": [
    "Java",
    "Android SDK",
    "AndroidX",
    "Material Components",
    "ViewBinding",
    "Realm",
    "Firebase Authentication",
    "Firebase Realtime Database",
    "Gradle"
  ],
  "telemetryMatrix": {
    "projectType": "Native Android Mobile Application",
    "targetPlatform": "Android Smartphones & Tablets",
    "primaryDomain": "Personal Vault & Note Management",
    "architecturePipeline": "Activity UI + Realm + Firebase Auth",
    "testingAndAudit": "Verified",
    "projectStatus": "Completed",
    "projectYear": "2022"
  },
  "desktopMobileProjectInfo": {
    "applicationType": "Native Android Mobile App",
    "targetPlatform": "Android",
    "developmentStatus": "Completed",
    "developmentYear": "2022",
    "applicationCategory": "Personal Data & Note Management"
  },
  "desktopMobileBackground": "Managing personal notes, account references, and private reminders across unorganized text apps often leaves sensitive entries exposed or fragmented without structured access control. Users need a dedicated mobile workspace that separates authenticated entry from persistent, instant on-device note retrieval.",
  "desktopMobileProblemStatements": [
    {
      "title": "Fragmented Personal Record Storage",
      "description": "General note applications rarely isolate sensitive credentials or account details behind dedicated account authentication and structured entry workflows.",
      "issueCode": "ISSUE_01"
    },
    {
      "title": "Latency & Offline Availability Gaps",
      "description": "Relying purely on remote network calls for every note read or edit slows down everyday lookup and prevents reliable access when mobile connectivity drops.",
      "issueCode": "ISSUE_02"
    },
    {
      "title": "Cluttered Note Modification Workflows",
      "description": "Mobile users need quick contextual actions to update or remove outdated personal records without navigating through complex multi-screen hierarchies.",
      "issueCode": "ISSUE_03"
    }
  ],
  "desktopMobileObjectives": [
    {
      "title": "Authenticated Account Access & Recovery",
      "description": "Implement email-and-password registration, sign-in, session sign-out, and password reset emails through Firebase Authentication and Realtime Database.",
      "targetTag": "TARGET_01"
    },
    {
      "title": "Reactive On-Device Note Persistence",
      "description": "Persist Note objects locally in an embedded Realm database with descending timestamp sorting and automatic RecyclerView UI updates via RealmChangeListener.",
      "targetTag": "TARGET_02"
    },
    {
      "title": "Focused Dark-Themed Mobile UX",
      "description": "Deliver cohesive dark gradient layouts, custom vector icons, ViewBinding forms, and long-press contextual edit/delete menus across Android API 24 to 32.",
      "targetTag": "TARGET_03"
    }
  ],
  "desktopMobileFeatures": [
    {
      "title": "Splash Router & Session Handling",
      "description": "Displays a 3-second branded splash screen and evaluates SharedPreferences session flags to direct users to either the vault dashboard or sign-in screen.",
      "badge": "Navigation"
    },
    {
      "title": "Firebase Account Authentication",
      "description": "Supports account creation, login, and password recovery email dispatch via FirebaseAuth while storing UserPersonal metadata in Firebase Realtime Database.",
      "badge": "Auth"
    },
    {
      "title": "Chronological Vault Dashboard",
      "description": "Displays saved Note cards in a RecyclerView sorted by createdTime descending, automatically refreshing when Realm transactions commit.",
      "badge": "Dashboard"
    },
    {
      "title": "Add & Edit Note Workflows",
      "description": "Provides dedicated AddNoteActivity and EditNoteActivity screens with input validation and synchronous or asynchronous Realm write transactions.",
      "badge": "CRUD"
    },
    {
      "title": "Long-Press Context Actions",
      "description": "Binds a PopupMenu to each RecyclerView item card in MyAdapter, enabling one-step EDIT navigation or immediate DELETE removal from Realm.",
      "badge": "Interaction"
    }
  ],
  "desktopMobileInterfaceShowcase": [
    {
      "imageUrl": "/images/projects/privena_personal_data_management/image01.webp"
    },
    {
      "imageUrl": "/images/projects/privena_personal_data_management/image02.webp"
    }
  ],
  "desktopMobileUserFlow": {
    "summary": "Users launch into a branded splash router that directs authenticated sessions to the vault dashboard or routes new sessions through Firebase sign-in, registration, or password recovery. Inside the dashboard, users create, inspect, edit, or delete timestamped Realm notes via long-press context menus.",
    "steps": [
      {
        "step": "01",
        "title": "Splash & Session Check",
        "description": "Splash displays the Privena branding for 3000ms and inspects SharedPreferences to route to Signin or Dashboard.",
        "actorOrNode": "Splash Activity"
      },
      {
        "step": "02",
        "title": "Account Authentication or Recovery",
        "description": "Users sign in, register a new UserPersonal profile, or trigger a password reset email via FirebaseAuth.",
        "actorOrNode": "Firebase Auth"
      },
      {
        "step": "03",
        "title": "Vault Dashboard & Note Creation",
        "description": "Dashboard loads sorted Note records from Realm and lets users open AddNoteActivity to commit new timestamped entries.",
        "actorOrNode": "Dashboard & Realm"
      },
      {
        "step": "04",
        "title": "Contextual Edit, Delete & Sign-Out",
        "description": "Long-pressing a card opens a PopupMenu to launch EditNoteActivity or delete the record, while Log Out ends the Firebase session.",
        "actorOrNode": "MyAdapter & UI Thread"
      }
    ]
  },
  "desktopMobileArchitecture": {
    "summary": "Privena follows an Android Activity-centric architecture backed by ViewBinding, RecyclerView adapters, and dual persistence layers. Firebase Authentication and Realtime Database handle user identity and account metadata, while an embedded Realm object database drives reactive local note CRUD operations.",
    "layers": [
      {
        "name": "Presentation & UI Layer",
        "role": "Renders dark-themed Android Activities, custom XML drawables, RecyclerView cards, and ViewBinding input forms",
        "tech": "Android SDK & ViewBinding",
        "components": ["Splash", "Signin", "Signup", "Forgot", "Dashboard", "MyAdapter"]
      },
      {
        "name": "Identity & Cloud Profile Layer",
        "role": "Manages email/password authentication, password recovery emails, and cloud user profile storage",
        "tech": "Firebase Auth & Realtime Database",
        "components": ["FirebaseAuth", "DatabaseReference", "UserPersonal"]
      },
      {
        "name": "Local Persistence Layer",
        "role": "Stores, queries, sorts, and updates private Note records locally with reactive change notifications",
        "tech": "Realm & SharedPreferences",
        "components": ["Note", "RealmResults", "RealmChangeListener", "SharedPreferences"]
      }
    ]
  },
  "desktopMobileDataManagement": {
    "storageType": "Embedded Realm Object Database & SharedPreferences",
    "stateEngine": "Android Activity Lifecycle & RealmChangeListener",
    "offlineSyncStrategy": "Local-first on-device Realm persistence for notes paired with online Firebase Auth and Realtime Database for user accounts",
    "cachingMechanism": "In-memory RealmResults live query results bound directly to RecyclerView adapter with SharedPreferences session flags"
  },
  "desktopMobilePlatformImplementation": [
    {
      "title": "Android ViewBinding & Resource System",
      "description": "Enables viewBinding in app/build.gradle for type-safe UI access in authentication activities alongside custom XML gradients, vector icons, and WebP launcher mipmaps.",
      "badge": "Android UI"
    },
    {
      "title": "Reactive Realm Transactions & Listeners",
      "description": "Combines synchronous Realm transactions for note creation and deletion with executeTransactionAsync updates and RealmChangeListener callbacks for zero-boilerplate list refreshes.",
      "badge": "Persistence"
    },
    {
      "title": "Gradle Multi-Plugin Build Pipeline",
      "description": "Integrates Android Gradle Plugin, realm-gradle-plugin, and com.google.gms.google-services with Firebase BoM dependency management targeting Android SDK 24 through 32.",
      "badge": "Build Pipeline"
    }
  ],
  "desktopMobileTechSpecs": {
    "programmingLanguage": "Java",
    "framework": "Android SDK",
    "localStorage": "Realm"
  },
  "desktopMobilePlatformSpecs": {
    "targetPlatform": "Android Mobile Devices",
    "packageFormat": "Android APK Package",
    "targetArchitecture": "Universal Android ABI",
    "buildFootprint": "Lightweight Native Android APK"
  }
}
```
