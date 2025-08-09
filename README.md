# AI Renovation App

This project uses custom scripts to avoid using `npx` for running Next.js commands and provides AI-powered renovation suggestions using OpenAI's API.

## Features

- 📸 **Photo Upload**: Upload multiple room photos with preview thumbnails
- 🤖 **AI Analysis**: Get AI-powered renovation suggestions using OpenAI's GPT-4 Vision
- 🎨 **Style Preferences**: Specify your preferred style, budget, and room type
- 📋 **Detailed Plans**: Receive comprehensive renovation plans including layout changes, color schemes, furniture placement, and more

## Setup

1. Install dependencies:
   ```bash
   npm install
   ```

2. Set up OpenAI API key:
   - Create a `.env.local` file in the root directory
   - Add your OpenAI API key:
     ```
     OPENAI_API_KEY=your_actual_openai_api_key_here
     ```
   - Get your API key from [OpenAI Platform](https://platform.openai.com/api-keys)

## Available Scripts

### Development
Start the development server:
```bash
npm run dev
```
This uses a custom script (`scripts/dev.js`) that directly calls the Next.js binary from `node_modules` without using `npx`.

### Build
Build the project for production:
```bash
npm run build
```
This uses a custom script (`scripts/build.js`) that directly calls the Next.js binary from `node_modules` without using `npx`.

### Start
Start the production server:
```bash
npm run start
```
This uses a custom script (`scripts/start.js`) that directly calls the Next.js binary from `node_modules` without using `npx`.

## API Endpoints

### POST /api/upload
Upload photos for renovation analysis:
- Accepts multiple image files
- Supports: jpeg, jpg, png, gif, webp
- Max file size: 10MB per file
- Max files: 10

### POST /api/renovation-plan
Generate AI-powered renovation suggestions:
- Requires: photo filenames and user preferences
- Returns: structured renovation plan with recommendations

## Custom Scripts

The project includes custom Node.js scripts in the `scripts/` directory that:
- Directly call the Next.js binary from `node_modules/.bin/next`
- Avoid the need for `npx` entirely
- Provide proper error handling and exit codes
- Maintain the same functionality as the original `npx` commands

## Project Structure

```
ai-renovation-app/
├── scripts/
│   ├── dev.js      # Custom development script
│   ├── build.js    # Custom build script
│   └── start.js    # Custom start script
├── pages/
│   ├── index.js    # Main application page
│   └── api/
│       ├── upload.js           # Photo upload API
│       └── renovation-plan.js  # AI renovation plan API
├── uploads/        # Temporary storage for uploaded files
├── package.json    # Project configuration
└── README.md       # This file
```

## Usage

1. **Upload Photos**: Click "Select Photos" to choose room images
2. **Set Preferences**: Fill out the preferences form (style, budget, room type)
3. **Generate Plan**: Click "Generate Renovation Plan" to get AI suggestions
4. **Review Results**: View detailed renovation recommendations

## Environment Variables

- `OPENAI_API_KEY`: Your OpenAI API key (required for AI features)
