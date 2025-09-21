---
# Leave the homepage title empty to use the site title
title: ""
date: 2022-10-24
type: landing

design:
  # Default section spacing
  #spacing:
  #  padding: [6, 6, 6, 6]

sections:
  - block: hero
    content:
      title: Suzanne Aldrich — Modern Infra Architect
      text: |-
        Strategic Solutions Engineer at Cloudflare with 20+ years in infrastructure and security. 
        I help organizations design secure, resilient architectures using Cloudflare’s connectivity cloud, Zero Trust services, and developer platform. 
        I’ve guided startups and enterprises through high-stakes PoCs, migrations, and transformations across DNS, AppSec, DDoS, and network modernization. 
        My focus: turning infrastructure fragility into business resilience.
      primary_action:
        text: '**Connect**'
        url: https://www.linkedin.com/in/suzannealdrich/
        icon: sparkles
      secondary_action:
        text: '**Contact**'
        url: /#contact
      announcement:
        text:  '🎤 I’ll be speaking at Cloudflare Connect Las Vegas — *Everything breaks eventually: Designing for resiliency beyond SASE*'
        link:
          text: View session details
          url: https://events.cloudflare.com/connect/2025/sessions/3269488
    design:
      background:
        gradient_end: '#ed4a72'
        gradient_start: '#004ba0'
        # Text color (true=light, false=dark, or remove for the dynamic theme color).
        text_color_light: true
  - block: resume-biography-3
    id: about
    content:
      # The user's folder name in `content/authors/`
      username: suzanne
      # Show a call-to-action button under your biography? (optional)
      # To link to a file, upload it to your `static/uploads/` folder
      button:
        text: Download CV
        url: files/cv.pdf
      headings:
        about: ''
        education: ''
        interests: ''
    # design:
    #   banner:
    #     # Upload a cover image to `assets/media/` folder and reference its filename here (optional)
    #     filename: ''
    #   biography:
    #     # Customize the CSS style of your biography text (optional)
    #     style: ''
    design:
      #spacing:
      #  padding: [6, 6, 6, 6]
      #biography:
      #  style: 'text-align: justify; font-size: 0.8em;'
      # Apply a gradient background
      # css_class: hbx-bg-gradient
      # Avatar customization
      avatar:
        size: large # Options: small (150px), medium (200px, default), large (320px), xl (400px), xxl (500px)
        shape: rounded # Options: circle (default), square, rounded
  - block: markdown
    content:
      title: '📚 My Research'
      subtitle: ''
      text: |-
        My work explores how internet infrastructure can be made **secure, performant, and resilient in the face of inevitable failure**. From expired certificates to congested transit providers, no system is perfect — but modern architectures can bend without breaking.

        Recent focus areas:
        - **Zero Trust adoption** across enterprises and regulated industries.  
        - **Resiliency patterns** in DNS, DDoS mitigation, and application security.  
        - **Connectivity cloud strategies** for multi-cloud, SaaS, and edge environments.  
        - **Human-centered design in technical tooling**, ensuring usability at scale.  

        I share findings through talks and workshops — most recently at **FutureCon Seattle 2025** and soon at **Cloudflare Connect Las Vegas**.  
        
        👉 Please reach out if you’d like to collaborate on research, panels, or community events!
    design:
      columns: '1'

  - block: cta-card
    content:
      title: "Debating Executive Control of the Internet"
      text: |-
        '&#8220;If government authority weren’t acting in good faith for the public welfare, they might find any legal or technical control over the Internet irresistible to abuse, especially if they weren’t knowledgeable of or concerned with the potential ramifications of exercising such power.&#8221;'
      button:
        text: "Read More"
        url: 'post/debating-executive-control-of-the-internet-a-critical-ethical-analysis-of-the-kill-switch-bill/'
    design:
      background:
        gradient_end: '#ed4a72'
        gradient_start: '#004ba0'
        # Text color (true=light, false=dark, or remove for the dynamic theme color).
        text_color_light: true
      spacing:
        padding: ["6", "6", "6", "6"]
  - block: cta-card
    content:
      title: "How an Equation Changed Warfare"
      text: |-
        '&#8220;It only takes one irrational leader to start a world war. It only took one equation to change warfare. As Einstein himself put it, &#8220;Politics are for the moment. An equation is for eternity&#8221;&#8221;'
      button:
        text: "Read More"
        url: 'post/how-an-equation-changed-warfare/'
    design:
      background:
        gradient_end: '#ed4a72'
        gradient_start: '#004ba0'
        # Text color (true=light, false=dark, or remove for the dynamic theme color).
        text_color_light: light
      spacing:
        padding: ["6", "6", "6", "6"]
  - block: cta-card
    content:
      title: "The Status of Women in Computer Science"
      text: |-
        '&#8220;The lack of female computer scientists can be attributed to the negative effects of cultural stereotypes, barriers in the educational system, and the small number of female role models for young women; outreach programs, increased awareness of the problem, and a changing economic climate may increase the percentage of women in computer science.&#8221;'
      button:
        text: "Read More"
        url: 'post/the-status-of-women-in-computer-science/'
    design:
      background:
        gradient_end: '#ed4a72'
        gradient_start: '#004ba0'
        # Text color (true=light, false=dark, or remove for the dynamic theme color).
        text_color_light: light
      spacing:
        padding: ["6", "6", "6", "6"]
  - block: cta-card
    content:
      title: "Ethereal Expression - The History and Significance of the Theremin"
      text: |-
        '&#8220;At the dawn of the age of electricity, a Russian physicist named Lev Terman developed a new instrument that would allow composers and performers to transcend musical limits.&#8221;'
      button:
        text: "Read More"
        url: 'post/ethereal-expression/'
    design:
      background:
        gradient_end: '#ed4a72'
        gradient_start: '#004ba0'
        # Text color (true=light, false=dark, or remove for the dynamic theme color).
        text_color_light: light
      spacing:
        padding: ["6", "6", "6", "6"]
  - block: collection
    id: posts
    content:
      title: Recent Posts
      subtitle: ''
      text: ''
      # Page type to display. E.g. post, talk, publication...
      page_type: post
      # Choose how many pages you would like to display (0 = all pages)
      count: 5
      # Filter on criteria
      filters:
        author: ""
        category: ""
        tag: ""
        exclude_featured: true
        exclude_future: false
        exclude_past: false
        publication_type: ""
      # Choose how many pages you would like to offset by
      offset: 0
      # Page order: descending (desc) or ascending (asc) date.
      order: desc
    design:
      # Choose a layout view
      view: date-title-summary
      # Reduce spacing
      spacing:
        padding: [6, 6, 6, 6]
  - block: collection
    id: featured
    content:
      title: Featured Publications
      filters:
        folders:
          - post
        featured_only: true
    design:
      view: article-grid
      columns: 4
  # - block: collection
  #   content:
  #     title: Recent Publications
  #     text: ""
  #     filters:
  #       folders:
  #         - publications
  #       exclude_featured: false
  #   design:
  #     view: citation
  - block: collection
    id: talks
    content:
      title: Recent & Upcoming Talks
      filters:
        folders:
          - talk
    design:
      view: citation
      columns: 1
  - block: contact
    id: contact
    content:
      title: Contact
      subtitle:
      text: |-
        Send me a message.
      # Contact (add or remove contact options as necessary)
      email: mail@suzanne.link
      phone: 
      appointment_url: 
      address:
        street: 
        city: 
        region: 
        postcode: 
        country:
        country_code: 
      directions: 
      office_hours:
      # Choose a map provider in `params.yaml` to show a map from these coordinates
      coordinates:
        latitude: '48.2883'
        longitude: '-122.6484'  
      contact_links:
        - icon: mastodon
          icon_pack: fab
          name: Toot Me
          link: 'https://hachyderm.io/@suzannealdrich'
        - icon: keybase
          icon_pack: fab
          name: Keybase Me
          link: 'https://keybase.io/suzannealdrich'
      # Automatically link email and phone or display as text?
      autolink: true
      # Email form provider
      form:
        provider: formspree
        formspree:
          id: 'xlezaeay'
        netlify:
          # Enable CAPTCHA challenge to reduce spam?
          captcha: false
    design:
      columns: '2'      
---
