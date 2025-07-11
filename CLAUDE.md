cat > CLAUDE.md << 'EOF'
### 🔄 Project Awareness & Context & Research - MICO Health App
- **Documentation is a source of truth** - Your knowledge is out of date, I will always give you the latest documentation before writing any files that use third party APIs - that information was freshly scraped and you should NOT use your own knowledge, but rather use the documentation as a source of absolute truth.
- **Always read PLANNING.md** at the start of a new conversation to understand MICO's architecture, health domain requirements, and user experience goals.
- **Check TASK.md** before starting a new task. If the task isn't listed, add it with a brief description and today's date.
- **Use consistent naming conventions, file structure, and architecture patterns** as described in PLANNING.md.
- **Health Data Privacy First** - All health-related features must comply with HIPAA guidelines and implement proper data encryption and user consent mechanisms.
- **AI Personalization** - Every AI feature should learn from user behavior while maintaining privacy. Use local processing when possible, encrypted cloud storage when necessary.
- **Voice-First Design** - All features should be accessible via voice commands. Design with conversation flow in mind, not just visual interfaces.
- **Real-time Adaptability** - Build systems that can instantly adapt to user context changes (injury, dietary restrictions, equipment availability, food spoilage, etc.).
- **Stick to OFFICIAL DOCUMENTATION PAGES ONLY** - For all research ONLY use official documentation pages. Use web search on the documentation page given to you and then create documentation in your memory, then choose the exact pages that make sense for this project and scrape them using web search tools.
- **Ultrathink** - Use deep thinking capabilities to decide which technologies to research, what information to put into PRPs, and how to build health-focused AI systems.
- **Create 2 documents .md files** - Phase 1 and phase 2 - phase 1 is skeleton code, phase 2 is complete production ready code with all health features and necessary mobile/backend implementations for production use.
- **Always research extensively when doing research** - If a page 404s or does not contain correct content, try to search again and find the actual page/content. Put the output of each successful web search into a new directory with the name of the technology researched, then inside it .md files of each output.
- **Refer to /research/ directory** - Before implementing any feature that uses something that requires documentation, refer to the relevant directory inside /research/ directory and use the .md files to ensure you're coding with great accuracy for health applications.
- **Health Domain Accuracy** - When implementing nutrition, fitness, or health features, always verify against authoritative sources (FDA, USDA, WHO, peer-reviewed research).
- **For Maximum efficiency, whenever you need to perform multiple independent operations, such as research, invoke all relevant tools simultaneously, rather than sequentially.**

### 🏥 Health App Specific Requirements - MICO
- **Precision Nutrition** - Use inventory-based nutrition tracking with photo validation, not just photo-only estimates. Maintain detailed nutritional databases with brand information.
- **Recipe Precision** - Calculate exact portions and nutritional values from known ingredients. Use photos for cross-referencing and validation, not primary calculation.
- **Fitness Science** - Base all exercise recommendations on peer-reviewed research. Include proper warm-up, cool-down, and injury prevention protocols.
- **Computer Vision Precision** - Food recognition must achieve >95% accuracy for common foods. Implement confidence scoring and user verification workflows.
- **Voice Context** - Maintain conversation context for natural health coaching interactions across multiple exchanges.
- **Adaptive AI** - Build systems that can intelligently substitute ingredients or modify routines based on user context and constraints.
- **Data Synchronization** - Health data must sync seamlessly across devices while maintaining privacy and handling offline scenarios.
- **Emergency Protocols** - Implement safety features for extreme calorie restriction detection, overexercise warnings, and emergency contact systems.

### 🧱 Code Structure & Modularity - MICO Tech Stack
- **Never create a file longer than 500 lines of code.** If a file approaches this limit, refactor by splitting it into modules or helper files.
- **Health Domain Separation** - Separate nutrition logic, fitness logic, AI personalization, and voice processing into distinct modules.
- **Always refer to the specific Phase document you are on** - If you are on phase 1, use phase-1.md, if you are on phase 2, use phase-2.md.
- **Next.js 15.3.5 Backend Architecture** - Use App Router with Server Components, Route Handlers for APIs, and proper file-system based routing.
- **Expo 53.0.19 Mobile Architecture** - Use Expo Router for navigation, React Native New Architecture by default, and platform-specific optimizations.
- **Organize code into clearly separated modules**, grouped by health domain responsibility:
    - `nutrition/` - Food recognition, calorie tracking, meal planning, grocery management
    - `fitness/` - Exercise routines, progress tracking, form analysis, injury prevention
    - `ai/` - Personalization engine, conversation flow, recommendation algorithms
    - `voice/` - Speech recognition, natural language processing, voice synthesis
    - `data/` - Health data models, sync logic, privacy controls, Supabase integrations
    - `integrations/` - Third-party APIs (fitness devices, nutrition databases, recipe APIs)
- **Use clear, consistent ES6 imports** (prefer relative imports within packages).
- **Use environment variables** for all API keys, database connections, and configuration with proper .env setup.
- **Privacy by Design** - Implement data minimization, user consent management, and opt-out mechanisms in every feature.

### 🎯 MICO AI Behavior Rules
- **Health Safety First** - Never provide medical advice. Always recommend consulting healthcare professionals for medical concerns.
- **Conversational Intelligence** - Understand context, remember user preferences, and adapt communication style to user's health literacy level.
- **Proactive Assistance** - Anticipate user needs based on time of day, workout schedule, meal timing, and personal patterns.
- **Adaptive Recommendations** - Instantly modify plans when user reports injuries, equipment unavailability, food allergies, or schedule changes.
- **Motivational Support** - Provide encouragement while being realistic about goals and progress timelines.
- **Cultural Sensitivity** - Respect dietary restrictions, cultural food preferences, and varying fitness customs.

### 🧪 Testing & Reliability - Health Focus
- **Always create Jest unit tests for health features** - nutrition calculations, fitness progressions, AI recommendations.
- **After updating any health logic**, verify against authoritative sources and update tests accordingly.
- **Health Data Accuracy Tests** - Include tests for:
    - Nutritional calculation accuracy (±5% margin for common foods)
    - Exercise form safety checks
    - Calorie burn estimation validation
    - Voice command recognition accuracy (>90% for health terms)
    - Food image classification precision
- **Tests should live in a /tests folder** mirroring the main app structure.
    - Include at least: 1 test for expected use, 1 edge case, 1 failure case
- **Privacy Compliance Testing** - Ensure data encryption, secure transmission, and proper data deletion workflows.
- **Performance Testing** - Voice responses <2 seconds, image recognition <3 seconds, AI recommendations <5 seconds.

### ✅ Task Completion - MICO
- **Mark completed tasks in TASK.md** immediately after finishing them.
- **Health Feature Validation** - Before marking health features complete, verify against:
    - FDA nutritional labeling requirements
    - Exercise science best practices
    - Accessibility guidelines for health apps
    - Privacy compliance checklists
- Add new sub-tasks or TODOs discovered during development to TASK.md under a "Discovered During Work" section.

### 📎 Style & Conventions - MICO Tech Stack
- **Use JavaScript/TypeScript** as the primary language for both Next.js backend and Expo frontend.
- **Follow ESLint rules**, use TypeScript where possible, and format with Prettier.
- **Use proper TypeScript type definitions** for health data models and API responses.
- **Next.js 15.3.5 Patterns** - Use App Router, Server Components, Route Handlers, and proper file-system routing conventions.
- **Expo 53.0.19 Patterns** - Use Expo Router for navigation, React Native New Architecture, and platform-specific code handling.
- **Health UI/UX Patterns** - Use familiar health app conventions (green for good, red for warnings, progress circles, etc.).
- Write **comprehensive JSDoc comments for every health function** using standard format:
  ```typescript
  /**
   * Calculates daily caloric needs based on user profile and activity level.
   * 
   * @param {UserProfile} userProfile - User's age, gender, height, weight, activity level
   * @param {Goals} goals - Weight loss/gain/maintenance goals
   * @returns {CaloricNeeds} Calculated daily caloric needs with macro breakdown
   * @throws {ValidationError} When user profile data is invalid
   * 
   * @example
   * ```typescript
   * const needs = calculateCaloricNeeds({
   *   age: 30, gender: 'female', height: 165, weight: 60, activityLevel: 'moderate'
   * }, { type: 'weight_loss', rate: 0.5 });
   * ```
   */
  ```

### 📱 React Native & Expo 53.0.19 Specific
- **Use Expo Router** for navigation in the mobile app with proper file-system routing.
- **Follow React Native New Architecture** - Enabled by default in SDK 53, use Fabric and TurboModules.
- **Use React Native components optimized** for mobile interfaces and health tracking.
- **Handle platform-specific code** appropriately (iOS vs Android) using Platform API.
- **Optimize for mobile performance** especially for image processing, AI features, and real-time health tracking.
- **Support offline functionality** - Core health features should work without internet connectivity.
- **Battery optimization** - Minimize battery drain from AI processing and background health monitoring.

### 🔗 Supabase Integration - All-in-One Backend
- **Use Supabase client** for all database operations with proper TypeScript types.
- **Implement Row Level Security (RLS)** for user health data protection and privacy.
- **Use Supabase Auth** for user authentication with health data considerations.
- **Leverage Supabase Edge Functions** for AI processing, health calculations, and real-time features.
- **Use Supabase Storage** for food images, workout videos, and user-generated health content.
- **Real-time subscriptions** for live health coaching, workout sessions, and progress tracking.
- **Health Data Encryption** - All sensitive health data must be encrypted at rest and in transit.

### 🎨 Design System - Tailwind CSS & shadcn/ui
- **Use Tailwind CSS utility-first approach** for rapid, consistent styling across Next.js and React Native.
- **Implement shadcn/ui components** built on Radix UI primitives for accessible, customizable components.
- **Health-focused color psychology** - Use colors that promote healthy behaviors (greens for nutrition, blues for hydration).
- **Mobile-first design** - Prioritize mobile experience for Expo app, ensure responsive design for Next.js.
- **Accessibility First** - Ensure all health features work for users with visual, auditory, or motor impairments.
- **Voice UI Design** - Design conversation flows that feel natural and support multi-turn health discussions.
- **Data Visualization** - Use Recharts for clear, motivating health analytics without overwhelming users.

### 📚 Documentation & Explainability - Health Context
- **Update README.md** when new health features are added, privacy policies change, or setup steps are modified.
- **Health Feature Documentation** - Every health calculation, AI recommendation, or safety feature must be thoroughly documented with scientific sources.
- **Privacy Documentation** - Maintain clear documentation of what health data is collected, how it's used, and user rights.
- **Comment health-critical code** with references to scientific sources and safety considerations.
- When writing complex health algorithms, **add inline `// Source:` comments** referencing peer-reviewed studies or official guidelines.

### 🧠 AI Behavior Rules - MICO Specific
- **Never assume missing health context. Ask clarifying questions** about dietary restrictions, injuries, medical conditions, or equipment availability.
- **Never hallucinate nutritional data or exercise recommendations** – only use verified, authoritative sources (USDA, FDA, peer-reviewed research).
- **Always confirm food identification accuracy** before providing nutritional information. Implement confidence thresholds and user verification.
- **Never delete or overwrite existing health data** unless explicitly instructed or as part of a user-initiated data management task.
- **Personalization Learning** - Continuously learn from user interactions while respecting privacy boundaries and health data regulations.
- **Safety Protocols** - Implement automatic checks for dangerous patterns (extreme calorie restriction, overexercise, injury risks).

### 🔒 Privacy & Security - Health Data Compliance
- **Encrypt all health data** at rest and in transit using industry-standard encryption.
- **Implement granular privacy controls** - users should control what health data is shared and with whom.
- **Data Minimization** - Only collect health data that's essential for app functionality.
- **Secure AI Processing** - Use on-device processing when possible, secure cloud processing (Supabase Edge Functions) when necessary.
- **Regular Security Audits** - Implement automated security testing and regular penetration testing.
- **Compliance Monitoring** - Ensure ongoing compliance with HIPAA, GDPR, and other relevant health data regulations.

### 🌐 Integration Guidelines - Health Ecosystem
- **Wearable Device Integration** - Support major fitness trackers and health monitoring devices.
- **Health Platform APIs** - Integrate with Apple HealthKit, Google Fit, and other health platforms.
- **Nutrition Databases** - Use USDA FoodData Central, Edamam, or similar authoritative sources.
- **Recipe APIs** - Integrate with recipe databases that provide accurate nutritional information.
- **Grocery APIs** - Connect with grocery delivery services and store inventory systems.
- **Fitness Equipment APIs** - Support smart gym equipment and home fitness devices.

### 🤖 Voice Interface Specifications - Natural Health Coaching
- **Natural Conversation** - Support natural language queries about health, nutrition, and fitness using advanced AI models.
- **Context Awareness** - Understand user context (time of day, location, recent activities, health goals).
- **Multi-Turn Dialogues** - Handle complex health conversations that span multiple exchanges with context retention.
- **Voice Training** - Allow users to train voice recognition for improved accuracy with health terminology.
- **Noise Handling** - Function effectively in gym, kitchen, and outdoor environments with noise cancellation.
- **Hands-Free Operation** - Enable complete app control through voice for accessibility and convenience during workouts/cooking.

### 🔬 AI/ML Model Guidelines - Health AI
- **Health-Specific Models** - Use models trained on health and nutrition data for better accuracy in recommendations.
- **Bias Testing** - Regularly test AI models for bias across different demographics, health conditions, and cultural backgrounds.
- **Model Updates** - Implement safe model update mechanisms that don't compromise user health data.
- **Explainable AI** - Provide clear explanations for AI health recommendations, especially nutrition and fitness advice.
- **Continuous Learning** - Implement federated learning or similar privacy-preserving learning mechanisms for personalization.
- **Safety Constraints** - Build hard constraints into AI models to prevent dangerous health recommendations.

### 📊 Data Visualization - Health Analytics
- **Use Recharts** for creating intuitive health progress charts, nutrition breakdowns, and fitness analytics.
- **Progress Tracking** - Visual representations of health goals, workout progress, and nutritional achievements.
- **Real-time Updates** - Charts should update in real-time as users log health data throughout the day.
- **Accessibility** - Ensure charts are accessible to users with visual impairments using proper ARIA labels.
- **Mobile Optimization** - Charts must be touch-friendly and readable on mobile devices.
