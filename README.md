# Screenshot Capture Web App

![Screenshot Capture App](https://images.unsplash.com/photo-1551650975-87deedd944c3?w=1200&h=300&fit=crop&auto=format)

A powerful web application that captures high-quality screenshots from any webpage URL and automatically saves them to your Cosmic media library. Features both a user-friendly web interface and REST API endpoint for programmatic access.

## Features

- 📸 **One-Click Screenshot Capture** - Simple URL input with instant screenshot generation
- ☁️ **Automatic Cosmic Upload** - Screenshots automatically saved to your Cosmic media library
- 🔗 **API Endpoint Access** - RESTful API for programmatic screenshot capture
- 🖼️ **High-Quality Images** - Full-page screenshots with customizable dimensions
- 📱 **Responsive Design** - Works perfectly on desktop and mobile devices
- 🎯 **Gallery View** - Browse and manage all captured screenshots
- ⬇️ **Download & Share** - Direct download links and sharing capabilities

## Clone this Bucket and Code Repository

Want to create your own version of this project with all the content and structure? Clone this Cosmic bucket and code repository to get started instantly:

[![Clone this Bucket and Code Repository](https://img.shields.io/badge/Clone%20this%20Bucket-29abe2?style=for-the-badge&logo=cosmic&logoColor=white)](https://app.cosmic-staging.com/projects/new?clone_bucket=6880179201d6b9914ef1f05e&clone_repository=68801dbe17ea59ba72238333)

## Prompts

This application was built using the following prompts to generate the content structure and code:

### Content Model Prompt

> No content model prompt provided - app built from existing content structure

### Code Generation Prompt

> Build a webapp that can capture a screenshot from a webpage URL and save to the cosmic bucket media. Make a UI located on the home page with text input and an API endpoint that functions the same to take a URL and upload screenshot.

The app has been tailored to work with your existing Cosmic content structure and includes all the features requested above.

## Technologies Used

- **Next.js 15** - React framework with App Router
- **TypeScript** - Type-safe development
- **Tailwind CSS** - Utility-first CSS framework
- **Cosmic SDK** - Content management and media uploads
- **Puppeteer** - Headless browser for screenshot capture
- **React** - Component-based UI library

## Prerequisites

- Node.js 18+ or Bun runtime
- A Cosmic account and bucket
- Basic knowledge of React/Next.js

## Getting Started

### Installation

1. Clone this repository
2. Install dependencies:
```bash
bun install
```

3. Set up your environment variables:
```bash
cp .env.example .env.local
```

4. Add your Cosmic credentials to `.env.local`:
```env
COSMIC_BUCKET_SLUG=your-bucket-slug
COSMIC_READ_KEY=your-read-key  
COSMIC_WRITE_KEY=your-write-key
```

5. Run the development server:
```bash
bun dev
```

6. Open [http://localhost:3000](http://localhost:3000) in your browser

## Cosmic SDK Examples

### Capture Screenshot via UI
1. Enter a webpage URL in the input field
2. Click "Capture Screenshot" button
3. Wait for the screenshot to be processed and uploaded
4. View the result in the gallery below

### API Endpoint Usage
```bash
# POST request to capture screenshot
curl -X POST http://localhost:3000/api/screenshot \
  -H "Content-Type: application/json" \
  -d '{"url": "https://example.com"}'
```

### Fetch Screenshots
```typescript
// Get all screenshots from Cosmic
const screenshots = await cosmic.objects.find({
  type: 'screenshots'
}).props(['title', 'slug', 'metadata'])
```

## Cosmic CMS Integration

This app automatically creates a "screenshots" object type in your Cosmic bucket to store:
- Original webpage URL
- Screenshot metadata (dimensions, file size)
- Capture timestamp
- Image file reference

Screenshots are uploaded to your Cosmic media library and optimized with imgix for fast delivery.

## API Documentation

### POST /api/screenshot

Capture a screenshot of any webpage URL.

**Request Body:**
```json
{
  "url": "https://example.com",
  "width": 1200,     // optional, defaults to 1200
  "height": 800,     // optional, defaults to 800
  "fullPage": true   // optional, defaults to true
}
```

**Response:**
```json
{
  "success": true,
  "data": {
    "id": "screenshot-id",
    "url": "original-url", 
    "imageUrl": "cosmic-media-url",
    "timestamp": "2024-01-01T00:00:00Z"
  }
}
```

## Deployment

### Vercel (Recommended)
1. Connect your repository to Vercel
2. Add environment variables in Vercel dashboard
3. Deploy automatically on push to main branch

### Environment Variables
Set these in your hosting platform:
- `COSMIC_BUCKET_SLUG`
- `COSMIC_READ_KEY`
- `COSMIC_WRITE_KEY`

<a
  href="https://www.cosmicjs.com?utm_source=bucket_screenshot-app&utm_medium=referral&utm_campaign=app_footer&utm_content=built_with_cosmic"
  target="_blank"
  rel="noopener noreferrer"
  className="bg-cosmic-dark hover:bg-cosmic-dark-hover text-white px-4 py-2 rounded-md text-sm font-medium no-underline inline-flex items-center gap-2 transition-colors duration-200"
>
  <img 
    src="https://cdn.cosmicjs.com/b67de7d0-c810-11ed-b01d-23d7b265c299-logo508x500.svg" 
    alt="Cosmic Logo" 
    className="w-5 h-5"
  />
  Built with Cosmic
</a>
<!-- README_END -->