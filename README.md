# **Front-End Intern Task – User Form in Modal (TypeScript + Vanilla JS)**

---

## **Implementation Language**

The project **must** be implemented in **TypeScript**, compiled down to **vanilla JavaScript** for browser execution.

**Allowed Tools & Libraries:**

- **Tailwind CSS** for styling.
- **`zxcvbn`** for password strength checking.

**Prohibited:**

- Any JavaScript frameworks (React, Vue, Angular, etc.).
- Any other external libraries (except the two above).

---

## **Overview**

You will create a **responsive HTML form inside a modal** that allows adding a new user. The modal will be triggered by an **"Add User"** button and can be closed by:

- Clicking **"Cancel"** (clears all inputs).
- Successfully adding a user (validating, saving, closing).

The form will:

- Include **both HTML and JavaScript (TypeScript)** validation for each input.
- Store submitted data in **LocalStorage** as user objects.
- Style the UI entirely with **Tailwind CSS**.

---

## **Functional Requirements**

### **1. Modal Behavior**

- **Open**: Clicking "Add User" opens the modal.
- **Add**: Clicking "Add" validates data, saves to LocalStorage, closes modal.
- **Cancel**: Clicking "Cancel" closes modal and clears all inputs (reset to default values).

---

### **2. Input Fields** (Order of Appearance for Best UX/UI)

#### **1. First Name** (Required)

- Type: `text`
- Max Length: 50
- Validation: Only alphabetic characters (A–Z, a–z).

#### **2. Last Name** (Required)

- Type: `text`
- Same rules as First Name.

#### **3. Email** (Required)

- Type: `email`
- Must follow valid email format.

#### **4. Password** (Required)

- Type: `password`
- Min length: 8 characters.
- Checked with `zxcvbn`: Only `"medium"` or `"strong"` accepted.

#### **5. Date of Birth** (Required)

- Type: `date`
- Must be a past date and user must be at least 18 years old.

#### **6. Country** (Required)

- Type: Dropdown (`<select>`)
- Options loaded from API: `https://restcountries.com/v3.1/all`

#### **7. Favorite Color** (Optional)

- Type: `color`
- Default Value: `#000000`

#### **8. Who am I** (Optional)

- Type: `textarea`
- Default Value: `""` (empty string).

#### **9. Profile Photo** (Optional)

- Type: `file` (image only)
- Accept formats: `.jpg`, `.jpeg`, `.png`
- Max size: 80 KB
- Default Value: `"no-photo"`

---

### **3. Validation Rules**

- **Dual Validation**: Each field must have:
  1. **HTML-level validation** using attributes like `required`, `pattern`, `maxlength`.
  2. **JavaScript-level validation** in the TypeScript code for deeper logic (regex checks, async checks, password strength).
- **Real-Time**: Errors shown while typing.
- **On Submission**: All fields rechecked before saving.
- **Error Display**: Use Tailwind classes to highlight invalid fields (`border-red-500`, etc.).

---

### **4. Storage Behavior (LocalStorage)**

- Save each valid submission as a **user object** with a unique ID.
- Allow **Create**:
  - **Create**: Add new user.
- After successful **Add**, **reset** the form to default values.

---

### **5. Default Values for Optional Fields**

- **Favorite Color**: `#000000`
- **Who am I**: `""`
- **Profile Photo**: `"no-photo"` placeholder

---

## **Coding Standards**

- **Clean Code**:
  - Reusable functions.
  - Clear, descriptive variable names.
  - Consistent naming conventions (`camelCase` for variables/functions, `PascalCase` for types/interfaces).
- **Comments**:
  - Explain complex logic and validation checks.
- **Accessibility**:
  - Each input must have a unique `tabindex` in sequential order.
  - Use semantic HTML tags where possible (`<form>`, `<label>`, `<section>`, etc.).
- **Folder Structure**:
  ```
  /src
    index.html
    /ts
      main.ts
      validation.ts
    /css
      styles.css
  /dist
    main.js   (compiled TypeScript)
  tailwind.config.js
  tsconfig.json
  ```

---

## **Bonus Points**

- Use **Object-oriented programming** and **Functional programming** paradigms together
- Add light animations for modal open/close.
- Make the form responsive for mobile and desktop.
