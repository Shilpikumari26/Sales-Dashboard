📊 Eureka Club Sales Dashboard
A modern, responsive web-based sales analytics dashboard built for the Eureka Club Tech Team recruitment process.
📊 Dashboard Features Breakdown
1. Metrics Cards

Total Revenue: Displays formatted currency (e.g., $47,523.45)
Total Sales: Shows transaction count with comma formatting
Avg Order Value: Calculated revenue per transaction
Products Sold: Total quantity across all items

2. Sales Trend Chart

Type: Line chart with smooth curves
Aggregation: Monthly revenue totals
Features: Hover tooltips, responsive scaling
Styling: Custom colors matching brand theme

3. Regional Distribution

Type: Doughnut chart for better visual appeal
Data: Revenue by region (handles both "region" and "reigon" API inconsistencies)
Interactive: Hover effects with percentage display
Colors: Custom gradient palette

4. Top Products Ranking

Sorting: By total revenue (descending)
Display: Product name, units sold, revenue
Limit: Top 5 performers
Styling: Card-based layout with ranking numbers

5. Advanced Filtering

Region Filter: Dropdown with all available regions
Product Filter: Dropdown with all available products
Date Range: Start and end date pickers
Real-time Updates: All charts refresh instantly

6. Data Export

Format: CSV download
Content: Currently filtered dataset
Filename: sales_data.csv
Fields: All original data fields with proper formatting

🔧 Technical Implementation Details
Data Cleaning Strategy
javascript// Handles multiple data formats from API
const cleanedData = rawData.map(item => ({
    sale_id: item.sale_id || item.id,
    date: parseDate(item.date), // Handles both timestamps and ISO strings
    region: item.region || item.reigon || 'Unknown', // API inconsistency handling
    product: item.product,
    quantity: parseInt(item.quantity) || 0,
    unit_price: parseFloat(item.unit_price) || 0,
    total_price: parseFloat(item.total_price) || 0
}));
Chart.js Configuration

Responsive: maintainAspectRatio: false for proper scaling
Custom Styling: Brand-consistent color schemes
Smooth Animations: Tension curves and hover effects
Accessibility: Proper labels and contrast ratios

Performance Optimizations

Single API Call: Data fetched once and filtered client-side
Chart Destruction: Prevents memory leaks on filter changes
Debounced Updates: Efficient re-rendering on filter changes
Minimal DOM Manipulation: Updates content, not structure

🎨 Design Philosophy
Visual Hierarchy

Header: Bold branding with gradient background
Filters: Prominent but not overwhelming
Metrics: Eye-catching cards with key numbers
Charts: Clean, professional visualizations
Details: Additional insights in structured format

Color Scheme

Primary: #667eea to #764ba2 (Blue to Purple gradient)
Secondary: #28a745 (Success green for exports)
Neutral: #f8f9fa (Light backgrounds)
Text: #2c3e50 (Dark blue for readability)

Typography

Headers: Bold, large fonts for impact
Data: Monospace-style for numbers
Labels: Medium weight for clarity
Body: Clean, readable sans-serif

🚀 Deployment Instructions
Vercel Deployment (Step-by-Step)

Prepare Files:

   your-project-folder/
   ├── index.html
   └── README.md

Deploy via Vercel Website:

Go to vercel.com
Click "New Project"
Upload your folder
Click "Deploy"
Copy the live URL


Deploy via CLI (Alternative):

bash   npm i -g vercel
   cd your-project-folder
   vercel
GitHub Repository Setup

Create Repository:

bash   git init
   git add .
   git commit -m "Initial commit: Eureka Sales Dashboard"
   git branch -M main
   git remote add origin [your-repo-url]
   git push -u origin main

Enable GitHub Pages (Optional):

Go to repository settings
Scroll to "Pages" section
Select source branch (main)
Access via: https://yourusername.github.io/eureka-sales-dashboard



🧪 Testing Scenarios
Data Validation

Empty API Response: Graceful error handling
Malformed Data: Data cleaning and validation
Network Issues: Loading states and retry logic
Date Edge Cases: Various date format handling

User Interactions

Filter Combinations: All filter permutations work
Chart Interactions: Hover states and responsiveness
Export Functionality: CSV generation and download
Mobile Experience: Touch-friendly interface

Performance Testing

Large Datasets: Efficient handling of 100+ records
Filter Speed: Instant updates without lag
Memory Usage: No memory leaks on repeated interactions
Load Times: Fast initial page load

📱 Mobile Responsiveness
Breakpoints

Desktop: > 768px - Full grid layout
Tablet: 768px - Stacked charts
Mobile: < 768px - Single column layout

Mobile Optimizations

Touch Targets: 44px minimum for buttons
Readable Text: Scalable font sizes
Simplified Filters: Stacked layout for better UX
Chart Scaling: Properly sized for small screens

🔐 Security Considerations
Client-Side Security

XSS Prevention: Proper HTML escaping
Data Validation: Input sanitization
HTTPS Only: Secure API communications
No Sensitive Data: All client-side processing

🚦 Browser Compatibility
Supported Browsers

Chrome: 90+ ✅
Firefox: 88+ ✅
Safari: 14+ ✅
Edge: 90+ ✅

Polyfills Used

fetch(): For older browser support
ES6 Features: Arrow functions, template literals
CSS Grid: Fallbacks for older browsers

📈 Future Enhancements
Potential Improvements

Real-time Updates: WebSocket integration for live data
Advanced Analytics: Predictive analytics and forecasting
User Authentication: Role-based access control
Data Sources: Multiple API endpoint support
Custom Date Ranges: Quarter, year-to-date selections
Drill-down Analysis: Click charts for detailed views

Scalability Considerations

Backend Integration: Database optimization for larger datasets
Caching Strategy: Redis/CDN for improved performance
API Rate Limiting: Handling large-scale usage
Progressive Loading: Pagination for massive datasets

🎯 Interview Preparation
Key Points to Discuss

Problem-Solving: How you handled API data inconsistencies
Design Decisions: Why you chose specific chart types
Performance: Client-side filtering vs server-side processing
User Experience: Mobile-first responsive design approach
Code Quality: Error handling and data validation strategies

Potential Questions & Answers

Q: "Why did you choose Chart.js over other libraries?"
A: "Chart.js provides excellent documentation, wide browser support, and the specific chart types needed (line, doughnut) with minimal bundle size."
Q: "How would you handle much larger datasets?"
A: "Implement server-side pagination, add virtual scrolling for lists, consider data aggregation at the API level, and add loading states for better UX."
Q: "What security considerations did you implement?"
A: "Input sanitization, XSS prevention through proper HTML escaping, HTTPS API calls, and client-side validation."

📞 Support & Contact
For any questions about this implementation:

GitHub Issues: [Create an issue in your repository]
Documentation: This README covers all implementation details
Code Comments: Inline documentation explains complex logic


Built with ❤️ for the Eureka Club Tech Team Recruitment Process
*This dashboard demonstrates proficiency in modern web development, API integration, data visualization, and user experience design.*🚀 Live Demo
Deployed Link: [Add your Vercel deployment link here]
GitHub Repository: [Add your GitHub repo link here]
📋 Project Overview
This dashboard fetches sales data from the provided API and presents dynamic, insightful analytics including:

✅ Total Revenue calculation (sum of all sales)
✅ Sales trends over time (monthly line chart)
✅ Sales distribution by region (interactive pie chart)
✅ Top 5 selling products by revenue
✅ Advanced filtering by region, product, and date range
✅ CSV export functionality for filtered data
✅ Fully responsive design (mobile, tablet, desktop)

🛠️ Technology Stack

Frontend: HTML5, CSS3, JavaScript (ES6+)
Charts: Chart.js (v3.9.1)
Styling: Pure CSS with modern gradients and animations
API: REST API integration with error handling
Responsive: CSS Grid and Flexbox for all screen sizes

🎨 Features
Core Analytics

Real-time Metrics: Total revenue, sales count, average order value, products sold
Interactive Charts: Line chart for trends, doughnut chart for regional distribution
Top Products: Ranked list with revenue and quantity information

User Experience

Advanced Filtering: Multi-dimensional filtering (region, product, date range)
Data Export: CSV download functionality for filtered datasets
Loading States: Professional loading indicators and error handling
Mobile First: Responsive design optimized for all devices

Technical Excellence

Data Cleaning: Handles inconsistent API data formats automatically
Performance: Efficient data processing and chart rendering
Error Handling: Graceful handling of API failures
Accessibility: Semantic HTML and proper contrast ratios

🏗️ Implementation Approach
Data Processing

API Integration: Fetch data from the provided MockAPI endpoint
Data Standardization: Clean and normalize inconsistent data formats
Date Handling: Parse both timestamp and ISO date formats
Filtering Engine: Real-time data filtering without re-fetching

Chart Implementation

Sales Trends: Monthly aggregation with smooth line charts
Regional Analysis: Dynamic pie charts with custom color schemes
Top Products: Calculated rankings based on revenue performance

User Interface

Modern Design: Gradient backgrounds, glass-morphism effects
Interactive Elements: Hover effects, smooth transitions
Professional Layout: Grid-based responsive design
Intuitive Controls: Easy-to-use filter interface

📁 Project Structure
eureka-sales-dashboard/
│
├── index.html          # Complete single-file application
├── README.md          # This documentation
└── screenshots/       # (Optional) Dashboard screenshots
🚦 Getting Started
Local Development

Clone the repository:

bash   git clone [your-repo-url]
   cd eureka-sales-dashboard

Open index.html in your browser:

bash   # Option 1: Direct file opening
   open index.html
   
   # Option 2: Local server (recommended)
   python -m http.server 8000
   # Then visit http://localhost:8000
Deployment
Vercel (Recommended):

Install Vercel CLI: npm i -g vercel
Run: vercel in project directory
Follow prompts for deployment

Alternative Options:

Netlify: Drag and drop the folder
GitHub Pages: Push to GitHub and enable Pages
Firebase Hosting: Use Firebase CLI

🔍 API Integration
Endpoint: https://68d424b8214be68f8c6887f1.mockapi.io/api/eureka/tech/task/sales
Data Format:
javascript{
  "sale_id": 1,
  "date": "2025-08-18",
  "region": "West", 
  "product": "Headphones",
  "quantity": 7,
  "unit_price": 721.58,
  "total_price": 5051.06
}
The application handles data inconsistencies and multiple date formats automatically.
🎯 Key Metrics Calculated

Total Revenue: sum(total_price) across all filtered sales
Total Sales: Count of sales transactions
Average Order Value: total_revenue / total_sales
Products Sold: sum(quantity) across all items

