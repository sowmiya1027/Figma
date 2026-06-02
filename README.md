# Ex09 Event Registration Web Application
## Date:31/05/26

## AIM:
To design, develop and deploy a web application for event registration.

## DESIGN STEPS:

### Step 1:
Create a new frame.

### Step 2:
Select any one preset size of your choice.

### Step 3:
Select the shapes you need.

### Step 4:
Import images as needed.

### Step 5:
Create pages based on your need and link them.

### Step 6:

Validate the HTML and CSS code.

### Step 6:

Publish the website in the given URL.

## DESIGN TOOL:
Figma

## CODE:
## Frame 1:
```
import figma2 from "./figma-2.png";
import secLogo1 from "./sec-logo-1.png";
import textOnPath from "./text-on-path.svg";

const actionButtons = [
  {
    id: "login",
    label: "LOGIN",
    top: "top-[3000px]",
    textTop: "top-[3125px]",
    textLeft: "left-[1039px]",
    textWidth: "w-[657px]",
    tracking: "tracking-[11.47px]",
  },
  {
    id: "register",
    label: "REGISTER",
    top: "top-[3559px]",
    textTop: "top-[3645px]",
    textLeft: "left-[920px]",
    textWidth: "w-[942px]",
    tracking: "tracking-[0]",
  },
];

export const AndroidMedium = (): JSX.Element => {
  return (
    <main
      className="bg-m3-schemes-primary-fixed-dim w-full min-w-[2580px] min-h-[4590px] relative overflow-hidden"
      data-m3-mode="light"
      data-color-mode="SDS-light"
    >
      <header className="absolute top-0 left-0 w-[2580px] h-[521px]">
        <img
          className="absolute top-0 left-0 w-[2580px] h-[521px] aspect-[4.97] object-cover"
          alt="Saveetha Engineering College header"
          src={secLogo1}
        />
      </header>
      <section
        className="absolute top-[863px] left-[576px]"
        aria-labelledby="visionx-summit-title"
      >
        <h1
          id="visionx-summit-title"
          className="h-[50px] flex items-center [font-family:'Inter-SemiBold',Helvetica] font-semibold text-black text-9xl tracking-[8.96px] leading-[50px] whitespace-nowrap m-0"
        >
          VISIONX SUMMIT 26
        </h1>
      </section>
      <section
        className="absolute top-[1255px] left-[283px] w-[2130px] h-[1402px]"
        aria-label="Event poster"
      >
        <img
          className="absolute top-0 left-0 w-[2130px] h-[1402px] aspect-[1.52] object-cover"
          alt="Artificial intelligence themed event visual"
          src={figma2}
        />
      </section>
      <img
        className="absolute top-[2442px] left-[1446px] w-[1067px] h-[1067px] pointer-events-none"
        alt=""
        aria-hidden="true"
        src={textOnPath}
      />
      <nav className="absolute inset-0" aria-label="Primary actions">
        {actionButtons.map((button) => (
          <button
            key={button.id}
            type="button"
            aria-label={button.label}
            className={`absolute left-[430px] w-[1808px] h-[424px] bg-color-icon-utilities-icon-on-measurement cursor-pointer transition-opacity duration-200 hover:opacity-95 focus-visible:opacity-95 focus-visible:outline focus-visible:outline-4 focus-visible:outline-white ${button.top}`}
          >
            <span
              className={`absolute ${button.textTop} ${button.textLeft} ${button.textWidth} [font-family:'Lexend_Exa-Regular',Helvetica] font-normal text-white text-9xl leading-[normal] ${button.tracking}`}
            >
              {button.label}
            </span>
          </button>
        ))}
      </nav>
    </main>
  );
};

export default AndroidMedium;
```

## Frame 2:
```
import fig1 from "./fig-1.png";
import secLogo2 from "./sec-logo-2.png";

export const AndroidCompact = (): JSX.Element => {
  const pageTitle = "EVENTS";

  return (
    <main className="bg-m3-schemes-inverse-primary w-full min-w-[2421px] min-h-[4590px] flex flex-col">
      <header className="flex flex-col">
        <img
          className="w-[2359px] h-[480px] mt-2.5 aspect-[4.97] object-cover"
          alt="Saveetha Engineering College header logo"
          src={secLogo2}
        />
      </header>
      <section aria-labelledby="events-heading" className="flex flex-col">
        <h1
          id="events-heading"
          className="ml-[811px] w-[595px] h-40 mt-[191px] [font-family:'Lexend_Exa-Regular',Helvetica] font-normal text-black text-9xl tracking-[0] leading-[normal]"
        >
          {pageTitle}
        </h1>
      </section>
      <section aria-label="Events banner" className="flex flex-col">
        <img
          className="ml-[46px] w-[2240px] h-[1493px] mt-[2120px] aspect-[1.5] object-cover"
          alt="Crowd at an event with raised hands under blue stage lights"
          src={fig1}
        />
      </section>
    </main>
  );
};

export default AndroidCompact;
```

## Frame 3:
```
import { FormEvent, useId, useState } from "react";
import secLogo3 from "./sec-logo-3.png";

type FormData = {
  name: string;
  registerNumber: string;
  yearOfStudy: string;
  email: string;
  eventName: string;
};

const initialFormData: FormData = {
  name: "",
  registerNumber: "",
  yearOfStudy: "",
  email: "",
  eventName: "",
};

export const AndroidCompact = (): JSX.Element => {
  const [formData, setFormData] = useState<FormData>(initialFormData);
  const formId = useId();

  const fields = [
    {
      key: "name" as const,
      label: "Name:",
      inputType: "text",
      autoComplete: "name",
      absoluteLabelClass:
        "absolute top-[1119px] left-16 [font-family:'Lexend_Peta-Regular',Helvetica] font-normal text-black text-9xl tracking-[0] leading-[normal]",
      absoluteInputClass:
        "absolute top-[1065px] left-[671px] w-[1835px] h-[334px] bg-colors-grays-white",
    },
    {
      key: "registerNumber" as const,
      label: "Register Number:",
      inputType: "text",
      autoComplete: "off",
      absoluteLabelClass:
        "absolute top-[1598px] left-16 w-[1988px] [font-family:'Lexend_Deca-Regular',Helvetica] font-normal text-black text-9xl tracking-[0] leading-[normal]",
      absoluteInputClass:
        "absolute top-[1609px] left-[1191px] w-[1315px] h-[261px] bg-colors-grays-white",
    },
    {
      key: "yearOfStudy" as const,
      label: "Year of Study:",
      inputType: "text",
      autoComplete: "off",
      absoluteLabelClass:
        "absolute top-[2105px] left-16 [font-family:'Lexend_Giga-Regular',Helvetica] font-normal text-black text-9xl tracking-[0] leading-[normal]",
      absoluteInputClass:
        "absolute top-[2105px] left-[1328px] w-[1178px] h-[274px] bg-colors-grays-white",
    },
    {
      key: "email" as const,
      label: "Email ID:",
      inputType: "email",
      autoComplete: "email",
      absoluteLabelClass:
        "absolute top-[2662px] left-16 [font-family:'Lexend_Giga-Regular',Helvetica] font-normal text-black text-9xl tracking-[0] leading-[normal]",
      absoluteInputClass:
        "absolute top-[2639px] left-[921px] w-[1585px] h-[260px] bg-colors-grays-white",
    },
    {
      key: "eventName" as const,
      label: "Event Name:",
      inputType: "text",
      autoComplete: "off",
      absoluteLabelClass:
        "absolute top-[3129px] left-16 [font-family:'Lexend_Giga-Regular',Helvetica] font-normal text-black text-9xl tracking-[0] leading-[normal]",
      absoluteInputClass:
        "absolute top-[3085px] left-[1191px] w-[1315px] h-[310px] bg-colors-grays-white",
    },
  ];

  const handleChange = (key: keyof FormData, value: string) => {
    setFormData((prev) => ({
      ...prev,
      [key]: value,
    }));
  };

  const handleSubmit = (event: FormEvent<HTMLFormElement>) => {
    event.preventDefault();
  };

  return (
    <main
      className="bg-m3-schemes-inverse-primary w-full min-w-[2506px] min-h-[4565px] relative"
      data-m3-mode="light"
    >
<header>
<img
          className="absolute top-0 left-0 w-[2506px] h-[519px] aspect-[4.97] object-cover"
          alt="Saveetha Engineering College banner"
          src={secLogo3}
        />
</header>
<form
        className="relative w-full min-w-[2506px] min-h-[4565px]"
        onSubmit={handleSubmit}
      >
{fields.map((field) => {
          const inputId = `${formId}-${field.key}`;

          return (
            <div key={field.key}>
<label htmlFor={inputId} className={field.absoluteLabelClass}>
{field.label}
              </label>
<div className={field.absoluteInputClass}>
<input
                  id={inputId}
                  name={field.key}
                  type={field.inputType}
                  autoComplete={field.autoComplete}
                  value={formData[field.key]}
                  onChange={(event) => handleChange(field.key, event.target.value)}
                  aria-label=
                  className="w-full h-full px-10 py-6 [font-family:'Lexend_Deca-Regular',Helvetica] font-normal text-black text-7xl tracking-[0] leading-[normal] placeholder:text-black/40"
                />
</div>
</div>
);
        })}

        <button
          type="submit"
          className="absolute top-[3717px] left-[362px] w-[2044px] h-[645px] bg-color-icon-danger-on-danger rounded-[1022px/322.5px] flex items-center justify-center"
          aria-label="Register"
        >
<span className="[font-family:'Lexend_Giga-ExtraBold',Helvetica] font-extrabold text-black text-9xl tracking-[0] leading-[normal]">
REGISTER
          </span>
</button>
</form>
</main>
);
};

export default AndroidCompact;
```

## Frame 4:
```
import secLogo4 from "./sec-logo-4.png";
import success1 from "./success-1.png";

const pageImages = [
  {
    src: secLogo4,
    alt: "Saveetha Engineering College banner",
    className:
      "block w-[2632px] h-[563px] max-w-none aspect-[4.97] object-cover",
  },
  {
    src: success1,
    alt: "VisionX Summit 2026 registration successful poster",
    className:
      "block w-[2632px] h-[4058px] max-w-none aspect-[0.67] object-cover",
  },
];

export const AndroidCompact = (): JSX.Element => {
  return (
    <main
      className="bg-m3-schemes-inverse-primary w-full min-w-[2632px] min-h-[4621px] flex flex-col"
      data-m3-mode="light"
      aria-label="Registration success page"
    >
      {pageImages.map((image) => (
        <img
          key={image.alt}
          className={image.className}
          alt={image.alt}
          src={image.src}
          loading="eager"
          decoding="async"
        />
      ))}
    </main>
  );
};

export default AndroidCompact;
```

## OUTPUT:
![alt text](<Screenshot 2026-06-01 203329-1.png>)

## RESULT:
The program to design, develop and deploy a web application for event registration is completed successfully.
