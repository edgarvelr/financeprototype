# City of Miami Financial Information Portal

A modern, responsive web application providing access to the City of Miami's key financial documents and reports. Built with HTML, Tailwind CSS, and Alpine.js for a seamless user experience.

## Features

- **Responsive Design**: Optimized for desktop, tablet, and mobile devices
- **Dark Mode Toggle**: User-friendly dark/light theme switching
- **Tabbed Navigation**: Organized content sections for easy browsing
- **Accordion Menus**: Collapsible sections for better content organization
- **PDF Document Access**: Direct links to financial reports and documents
- **Modern UI/UX**: Clean, professional interface using Tailwind CSS

## Available Content

### Policies and Procedures
- Debt Management Policy
- Investment Policy

### EORT Actuarial Valuation Reports
- Annual reports from 2013-2024

### Cost Allocation Plans
- Fiscal year plans from 2015-2025

### Monthly Financial Reports
- Monthly reports organized by year (2016-2025)
- Collapsible accordion interface for easy navigation

### Annual Reports
- **CAFR (Comprehensive Annual Financial Reports)**: 2003-2024
- **PAFR (Popular Annual Financial Reports)**: 2004-2024
- **Single Audit Reports**: 2003-2024
- **Management Letters**: 2006-2024
- **Supplemental Reports to Bond Holders**: 2003-2024

### Debt Management
- **Summary of Outstanding Debt**: 2003-2023
- **Debt Ratios**: 2003-2023

## Technology Stack

- **HTML5**: Semantic markup structure
- **Tailwind CSS**: Utility-first CSS framework for styling
- **Alpine.js**: Lightweight JavaScript framework for interactivity
- **Google Fonts**: Inter and Merriweather for typography

## Getting Started

1. **Clone the repository**:
   ```bash
   git clone https://github.com/edgarvelr/financeprototype.git
   cd financeprototype
   ```

2. **Open the application**:
   - Simply open `index.html` in your web browser
   - No build process or server setup required

3. **Development**:
   - Edit `index.html` to modify content or styling
   - The application uses CDN links for all dependencies

## Browser Support

- Chrome
- Firefox
- Safari
- Edge
- Mobile browsers (iOS Safari, Chrome Mobile)

## Customization

### Adding New Content
1. Locate the appropriate tab section in `index.html`
2. Add new list items following the existing pattern:
   ```html
   <li><a href="path/to/document.pdf" target="_blank" class="list-item-link">
       <strong>Document Title</strong>
       <span class="text-blue-600 font-semibold">View PDF</span>
   </a></li>
   ```

### Styling Modifications
- Modify the `<style>` section in the HTML file
- Update Tailwind classes for layout changes
- Customize dark mode colors in the CSS variables

## License

This project is maintained by the City of Miami. All rights reserved.

## Contributing

For questions or suggestions regarding the City of Miami's financial information, please contact the appropriate department through the official City of Miami website.

## Contact

- **Website**: [www.miamigov.com](http://www.miamigov.com)
- **Email**: webmaster@miamigov.com
- **ADA Support**: [ADA Public Notice](http://www.miamigov.com/ADA/Pages/PublicNotice/Policy.asp)

---

*Last updated: January 2025* 