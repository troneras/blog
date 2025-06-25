# 🚀 Troneras Blog

Personal blog of Antonio Blázquez (Troneras) - Built with Astro and Tailwind CSS.

## About

This is my personal blog where I share thoughts, experiences, and insights on technology, software development, and life. The blog is built using modern web technologies focusing on performance, accessibility, and clean design.

## Features

- ✅ **Fast and SEO friendly** blog with automatic RSS feed
- ✅ **Dark mode** support
- ✅ **Image optimization** using Astro Assets
- ✅ **MDX support** for rich content
- ✅ **Categories & Tags** for better organization
- ✅ **Social sharing** integration
- ✅ **Analytics** ready (Google Analytics, Splitbee)
- ✅ **Responsive design** for all devices

## Tech Stack

- **[Astro](https://astro.build/)** - Static site generator
- **[Tailwind CSS](https://tailwindcss.com/)** - Utility-first CSS framework
- **[TypeScript](https://www.typescriptlang.org/)** - Type safety
- **[MDX](https://mdxjs.com/)** - Markdown with JSX support

## Getting Started

### Prerequisites

- Node.js 18.17.1 or higher
- npm or yarn

### Installation

1. Clone the repository:

```bash
git clone https://github.com/troneras/blog.git
cd blog
```

2. Install dependencies:

```bash
npm install
```

3. Start the development server:

```bash
npm run dev
```

4. Open [http://localhost:4321](http://localhost:4321) in your browser.

### Available Commands

| Command           | Action                                       |
| :---------------- | :------------------------------------------- |
| `npm install`     | Installs dependencies                        |
| `npm run dev`     | Starts local dev server at `localhost:4321`  |
| `npm run build`   | Build your production site to `./dist/`      |
| `npm run preview` | Preview your build locally, before deploying |
| `npm run check`   | Check your project for errors                |
| `npm run fix`     | Run Eslint and format codes with Prettier    |

## Project Structure

```
/
├── public/           # Static assets
├── src/
│   ├── assets/       # Images, styles, favicons
│   ├── components/   # Reusable components
│   ├── content/      # Blog posts (MDX/MD files)
│   ├── layouts/      # Page layouts
│   ├── pages/        # Route pages
│   ├── utils/        # Utility functions
│   └── config.yaml   # Site configuration
├── package.json
└── astro.config.ts
```

## Configuration

The main configuration file is `src/config.yaml`. You can customize:

- Site name and metadata
- SEO settings
- Blog configuration
- Social media links
- Analytics settings

## Deployment

This blog can be deployed to various platforms:

- **Vercel**: Connect your GitHub repository
- **Netlify**: Drag and drop the `dist` folder
- **GitHub Pages**: Use the GitHub Actions workflow
- **Any static hosting**: Upload the `dist` folder

## Contributing

While this is a personal blog, I welcome feedback and suggestions. Feel free to:

- Report bugs or issues
- Suggest improvements
- Share ideas for new features

## License

This project is open source and available under the [MIT License](LICENSE.md).

## Connect

- **Blog**: [troneras.com](https://troneras.com)
- **X (Twitter)**: [@\_troneras](https://x.com/troneras)
- **GitHub**: [github.com/troneras](https://github.com/troneras)
- **Email**: hello@_troneras.com

---

_Built with ❤️ using Astro and Tailwind CSS_
