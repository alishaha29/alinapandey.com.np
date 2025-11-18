# Alina Pandey - Personal Website

A minimalist, professional website showcasing expertise in International Law and Global Politics with a clean green theme.

## Features

- **Minimalist Design**: Clean, professional layout with focus on content
- **Green Color Theme**: Sophisticated green palette reflecting professionalism
- **Responsive**: Fully responsive design that works on all devices
- **Separate Writings Section**: Dedicated page for blogs and articles organized by category
- **Easy to Update**: Simple HTML structure for easy content management
- **Fast Loading**: Optimized CSS and minimal JavaScript for quick load times

## Website Structure

```
alinapandey.com.np/
├── index.html              # Main landing page
├── writings.html           # Blogs and articles page
├── css/
│   └── styles.css         # All styling with green theme
├── js/
│   └── main.js            # Interactive features
└── images/                # Placeholder for future images
```

## Sections

### Home Page (index.html)
1. **Hero Section**: Introduction and call-to-action
2. **About Section**: Background and mission statement
3. **Expertise Section**: Four key areas of focus
   - International Law
   - Global Politics
   - Legal Analysis
   - Policy Reform
4. **Writings Preview**: Link to full writings page
5. **Contact Section**: LinkedIn connection

### Writings Page (writings.html)
Organized into five categories:
1. **International Law**: Treaties and legal frameworks
2. **Policy Reform**: Policy analysis and recommendations
3. **Legal Analysis**: Case law and legislative commentary
4. **Global Politics**: Geopolitical insights
5. **Featured Publications**: Published works

## Adding New Articles

To add a new article to the writings page, replace a placeholder section with:

```html
<div class="article-card">
    <div class="article-meta">
        <span class="article-date">
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <rect x="3" y="4" width="18" height="18" rx="2" ry="2"></rect>
                <line x1="16" y1="2" x2="16" y2="6"></line>
                <line x1="8" y1="2" x2="8" y2="6"></line>
                <line x1="3" y1="10" x2="21" y2="10"></line>
            </svg>
            Month Day, Year
        </span>
        <span class="article-type">Article Type</span>
    </div>
    <h3><a href="link-to-article">Article Title</a></h3>
    <p class="article-excerpt">
        Brief summary of the article...
    </p>
    <a href="link-to-article" class="article-link">
        Read More
        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <line x1="5" y1="12" x2="19" y2="12"></line>
            <polyline points="12 5 19 12 12 19"></polyline>
        </svg>
    </a>
</div>
```

## Deployment Options

### Option 1: Traditional Web Hosting
1. Upload all files to your web hosting via FTP/SFTP
2. Ensure the domain `alinapandey.com.np` points to your hosting
3. Upload files to the public_html or www directory

### Option 2: GitHub Pages (Free)
1. Create a GitHub repository named `alinapandey.com.np`
2. Push all files to the repository
3. Enable GitHub Pages in repository settings
4. Configure custom domain in GitHub Pages settings
5. Update DNS records for alinapandey.com.np

### Option 3: Netlify (Recommended - Free)
1. Create a Netlify account
2. Drag and drop the website folder to Netlify
3. Configure custom domain `alinapandey.com.np`
4. Update DNS records as provided by Netlify

### Option 4: Vercel (Free)
1. Create a Vercel account
2. Import the project from GitHub or upload directly
3. Configure custom domain
4. Update DNS records

## DNS Configuration

Once your domain is activated, configure the following DNS records:

### For Netlify/Vercel:
- **A Record**: Point to hosting provider's IP
- **CNAME Record**: www → your-site.netlify.app (or vercel.app)

### For Traditional Hosting:
- **A Record**: Point to your hosting IP
- **CNAME Record**: www → alinapandey.com.np

## Customization

### Changing Colors
Edit the CSS variables in `css/styles.css`:
```css
:root {
    --primary-green: #2d5016;
    --secondary-green: #4a7c2c;
    --light-green: #7fa650;
    /* Adjust other colors as needed */
}
```

### Adding LinkedIn Profile Photo
1. Save your profile photo as `profile.jpg` in the `images/` folder
2. Add this code to the About section in `index.html`:
```html
<img src="images/profile.jpg" alt="Alina Pandey" class="profile-photo">
```

### Updating Contact Information
Edit the contact section in `index.html` to add email or other social links.

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## Performance

- Optimized CSS with minimal file size
- No external dependencies except Google Fonts
- Fast load times < 1 second
- Mobile-first responsive design

## Future Enhancements

Consider adding:
- Blog post pages (individual article pages)
- RSS feed for articles
- Newsletter subscription
- Search functionality
- Tags/categories filtering
- Dark mode toggle
- Analytics (Google Analytics or Plausible)

## Support

For questions or issues with the website:
- Review this README
- Check deployment documentation for your chosen hosting provider
- Verify DNS settings with your domain registrar

## License

© 2024 Alina Pandey. All rights reserved.

---

**Note**: This website is ready to deploy. Once your domain is activated, follow the deployment instructions above to make it live.
