# TeamStation-AI Documentation

CTO-grade docs for Axiom Cortex™ (Cognitive AI evaluation) and the Nearshore IT Co-Pilot™ platform.

🌐 **Live Documentation**: [https://teamstation-ai.github.io/docs](https://teamstation-ai.github.io/docs)

## About

This repository contains the official documentation for TeamStation-AI's flagship platforms:

- **Axiom Cortex™**: Cognitive AI evaluation and testing framework
- **Nearshore IT Co-Pilot™**: AI-powered nearshore development operations

## 🚀 Quick Start

Visit our [Getting Started Guide](https://teamstation-ai.github.io/docs/docs/getting-started/) to begin using our platforms.

## 🛠️ Local Development

### Prerequisites

- Ruby 2.5.0 or higher
- Bundler gem
- Jekyll gem

### Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/TeamStation-AI/docs.git
   cd docs
   ```

2. **Install dependencies**:
   ```bash
   bundle install
   ```

3. **Run the local server**:
   ```bash
   bundle exec jekyll serve
   ```

4. **View the site**:
   Open [http://localhost:4000/docs](http://localhost:4000/docs) in your browser

### Development Commands

```bash
# Serve with live reload (recommended for development)
bundle exec jekyll serve --livereload

# Serve with drafts
bundle exec jekyll serve --drafts

# Build the site (generates _site/ directory)
bundle exec jekyll build

# Clean generated files
bundle exec jekyll clean
```

## 📁 Project Structure

```
docs/
├── _config.yml          # Jekyll configuration
├── index.md             # Homepage
├── docs/                # Documentation pages
│   └── getting-started.md
├── _layouts/            # Page templates (if custom)
├── _includes/           # Reusable components (if custom)
├── _sass/               # Custom styles (if custom)
├── assets/              # Images, CSS, JS files
├── sitemap.xml          # SEO sitemap
├── robots.txt           # Search engine instructions
├── Gemfile              # Ruby dependencies
└── README.md            # This file
```

## 📝 Contributing

We welcome contributions to improve our documentation! Here's how you can help:

### Ways to Contribute

1. **Report Issues**: Found a bug or unclear documentation? [Open an issue](https://github.com/TeamStation-AI/docs/issues)
2. **Suggest Improvements**: Have ideas for better docs? [Start a discussion](https://github.com/TeamStation-AI/docs/discussions)
3. **Submit Changes**: Ready to contribute? Follow our contribution workflow below

### Contribution Workflow

1. **Fork the repository**
2. **Create a feature branch**:
   ```bash
   git checkout -b feature/improve-getting-started
   ```
3. **Make your changes**:
   - Write clear, concise documentation
   - Follow our [style guide](#writing-style-guide)
   - Test your changes locally
4. **Commit your changes**:
   ```bash
   git commit -m "docs: improve getting started guide clarity"
   ```
5. **Push and create a Pull Request**
6. **Wait for review** - we'll review and provide feedback

### Writing Style Guide

- **Clarity**: Write for your audience - assume basic technical knowledge
- **Structure**: Use headers, lists, and code blocks for readability
- **Tone**: Professional but approachable
- **Code Examples**: Always provide working, tested examples
- **Links**: Use descriptive link text, not "click here"

### Adding New Pages

1. Create your `.md` file in the appropriate directory
2. Add front matter with layout, title, and description:
   ```yaml
   ---
   layout: page
   title: Your Page Title
   description: Brief description for SEO
   permalink: /your-url-path/
   ---
   ```
3. Update navigation in `_config.yml` if needed
4. Test locally before submitting

## 🎨 Customization

### Themes and Styling

This site uses the Minima theme with GitHub Pages compatibility. To customize:

1. **Override theme files**: Create files in `_layouts/`, `_includes/`, or `_sass/`
2. **Add custom CSS**: Place files in `assets/css/`
3. **Modify configuration**: Update `_config.yml`

### SEO Optimization

The site includes:
- Jekyll SEO Tag plugin for meta tags
- Sitemap generation
- Robots.txt for search engines
- Open Graph and Twitter Card support

## 🔧 Troubleshooting

### Common Issues

**Jekyll build fails**:
```bash
# Update gems
bundle update

# Clean and rebuild
bundle exec jekyll clean
bundle exec jekyll build
```

**Pages not updating**:
- Check for syntax errors in front matter
- Ensure proper file naming conventions
- Clear browser cache

**Links broken**:
- Use relative links with baseurl: `{{ site.baseurl }}/path`
- Test all links in local development

### Getting Help

- 📧 **Documentation Issues**: [docs@teamstation.ai](mailto:docs@teamstation.ai)
- 💬 **Community Support**: [GitHub Discussions](https://github.com/TeamStation-AI/docs/discussions)
- 🐛 **Bug Reports**: [GitHub Issues](https://github.com/TeamStation-AI/docs/issues)

## 📄 License

This documentation is licensed under [MIT License](LICENSE).

## 🏢 About TeamStation-AI

TeamStation-AI is at the forefront of cognitive AI evaluation and nearshore IT operations. Learn more at [teamstation.ai](https://teamstation.ai).

---

**Happy documenting!** 📚✨
