## Description:
The QR Code with Logo provides powerful tools for creating customizable QR codes for various purposes, including URL links, text, emails, and vCards. It supports adding logos to QR codes, customizing colors, and more. You can create standard QR codes or advanced QR codes with personalized branding elements, making it ideal for marketing, digital business cards, and more.

## Key Features:
#### Standard QR Codes:
- Create simple QR codes for any URL or plain text content with customizable colors and quality.

#### QR Code with Logo:
- Add a custom logo in the center of your QR code. Supports logos up to 1MB in size, making it perfect for brand customization.

#### Email QR Codes:
- Generate QR codes that contain email information, including email address, subject, and body. Ideal for digital marketing or easy communication.

#### vCard QR Codes:
- Share contact information such as name, phone number, email, and address via a scannable vCard format QR code. Perfect for business networking.

#### Customizable Design:
- Easily customize the colors of your QR codes with options for both dark and light colors. You can also adjust the quality of the QR code by setting the number of pixels per module.

#### High-Resolution Output:
- The API returns high-quality PNG images, which can be used for both digital and print media.

## API Endpoints:

### 1. Create Standard QR Code
Generates a QR code from a URL or text.

- **Endpoint**: `POST /api/qr/create`
- **Request Body**:
```json
{
  "content": "https://www.example.com", // The URL or Text to be put in the QR
  "pixelsPerModule": 20, // Determines the quality of the QR. Increase value to increase quality
  "darkColorHex": "#000000", // Changes the color of the dark areas of the QR
  "lightColorHex": "#ffffff", // Changes the color of the dark areas of the QR
  "drawQuietZones": true // If true, adds the white border around QR (default true)
}
```
- **Response**:
```json
  A PNG image of the generated QR code
```

### 2. Create QR Code with Logo
Generates a QR code from a URL or text, with an optional logo in the center. The logo file must be uploaded as a form.


- **Endpoint**: `POST /api/qr/create`
- **Request Body (multipart/form-data)**:
```json
{
    "content": "https://www.example.com",
    "pixelsPerModule": 20,
    "darkColorHex": "#FF5733",
    "lightColorHex": "#ffffff",
    "iconSizePercentage": 20,
    "iconBorderWidth": 4
    "logo": [binary image file]  // Max 1MB Size
}
```
- **Response**:
```json
  A PNG image file with the generated QR code containing the logo.
```

### 3. Create Email QR Code
Generates a QR code that contains an email, subject, and body. Scanning the QR code will open the default email client with the provided details.

- **Endpoint**: `POST /api/qr/create`
- **Request Body**:
```json
{
  "email": "info@example.com",
  "subject": "Inquiry about your services",
  "body": "I am interested in learning more about your product."
}
```
- **Response**:
```json
 A PNG image of the generated email QR code.
```

### 4. Create vCard QR Code
Generates a QR code containing personal contact information in the vCard format. The vCard data can include full name, email, phone numbers, address, and more.


- **Endpoint**: `POST /api/qr/create`
- **Request Body**:
```json
{
  "fullName": "John Doe",
  "telephoneWork": "+123456789",
  "telephoneHome": "+987654321",
  "telephoneFax": "+123456788",
  "email": "john.doe@example.com",
  "organisation": "Example Corp",
  "title": "Software Engineer",
  "address": {
    "type": "WORK",
    "street": "123 Example St",
    "city": "Cityville",
    "state": "State",
    "postalCode": "12345",
    "country": "Country"
  },
  "url": "https://www.example.com"
}
```
- **Response**:
```json
 A PNG image of the generated vCard QR code.
```


## Why Choose This API?
- **Customizable**: Personalize your QR codes with logos, colors, and content types.
- **Flexible**: Generate QR codes for URLs, emails, vCards, and more.
- **Easy Integration**: Quick and simple API endpoints that can be easily integrated into your projects.
- **High Quality**: QR codes are generated in high resolution, ensuring crisp scans at any size.

## Pricing
We offer really affordable prices for our services. In fact, in all of our pricing plans, all features are unlocked. (Even in the free tier)
