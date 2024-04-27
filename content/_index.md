---
# Leave the homepage title empty to use the site title
title: ''
date: 2022-10-24
type: landing

sections:
  - block: hero
    demo: false # Only display this section in the Hugo Blox Builder demo site
    content:
      title: 'Solutions Engineering Leader'
      image:
        filename: avatar-hero.png
      cta:
        label: '**Hire Suzanne**'
        url: 'https://www.linkedin.com/in/suzannealdrich/'
      cta_alt:
        label: Ask her a question
        url: '/#contact'
      cta_note:
        label: >-
          <div style="text-shadow: none;"><a class="github-button" href="https://github.com/suzannealdrich/suzanne.link" data-icon="octicon-star" data-size="large" data-show-count="true" aria-label="Star">Star suzanne.link</a></div>
      text: |-
        Experienced engineering leader with 20+ years of focused expertise in technical product management and solutions engineering. I have a
        passion for learning and an interest in shaping technology's impact on society. I love bringing an innovative perspective to technical problems
        and helping customers realize the full value of technology.

        * I am known for a customer-obsessed approach with emphasis on human-centered design and usability for the web.
        * Design of Enterprise-grade scalable networks and compute systems that are secure, low-latency, reliable, and operate efficiently.
        * Deep technical experience with core web technologies including HTTP, DNS, TCP/IP, JavaScript, JSON, REST APIs.
        * Distributed computing including proxies, edge compute, content delivery & optimization, service workers, and other primitives.
        * Security capabilities including TLS & PKI with an emphasis on web security, including OWASP Top 10 and DDoS mitigation.
        * Modern web patterns including web server deployment with Nginx & Apache, CMS, JAMStack, PWA, React, and Next.JS.
        * Core systems design and engineering including operating systems, virtualization, containerization, database design, GitOps, cloud
        platforms, networking, and observability.

        <!--Custom spacing-->
        <div class="mb-3"></div>
        <!--GitHub Button JS-->
        <script async defer src="https://buttons.github.io/buttons.js"></script>
    design:
      background:
        gradient_end: '#ed4a72'
        gradient_start: '#004ba0'
        text_color_light: true
  - block: about.biography
    id: about
    content:
      title: Biography
      # Choose a user profile to display (a folder name within `content/authors/`)
      username: suzanne
  - block: skills
    content:
      title: Skills
      text: ''
      # Choose a user to display skills from (a folder name within `content/authors/`)
      username: suzanne
    design:
      columns: '1'
  - block: experience
    content:
      title: Experience
      # Date format for experience
      #   Refer to https://docs.hugoblox.com/customization/#date-format
      date_format: Jan 2006
      # Experiences.
      #   Add/remove as many `experience` items below as you like.
      #   Required fields are `title`, `company`, and `date_start`.
      #   Leave `date_end` empty if it's your current employer.
      #   Begin multi-line descriptions with YAML's `|2-` multi-line prefix.
      items:
        - title: Sales Engineering Manager, West
          company: Chronosphere
          company_url: 'https://www.chronosphere.io/'
          company_logo: org-chronosphere
          location: Remote
          date_start: '2022-09-12'
          date_end: '2023-07-17'
          description: Cloud native observability.
        - title: Director, Sales Engineering
          company: Vercel
          company_url: 'https://www.vercel.com/'
          company_logo: org-vercel
          location: Remote
          date_start: '2021-06-13'
          date_end: '2022-08-26'
          description: Enabling the world to ship the best products.
        - title: Field Solutions Engineer Manager
          company: Cloudflare
          company_url: 'https://www.cloudflare.com/'
          company_logo: org-cloudflare
          location: San Francisco, California
          date_start: '2015-07-14'
          date_end: '2021-06-01'
          description: To help build a better Internet.
        - title: Senior Customer Success Engineer
          company: Pantheon
          company_url: 'https://www.pantheon.io/'
          company_logo: org-pantheon
          location: San Francisco, California
          date_start: '2013-07-01'
          date_end: '2015-07-01'
          description: Drupal and WordPress hosting, automated DevOps, and scalable infrastructure serving billions of pageviews a month.
        - title: Owner
          company: SJA Consulting
          company_url: 'https://www.sjaconsulting.com/'
          company_logo: org-sja
          location: 
          date_start: '1997-06-01'
          date_end: ''
          description: Tech Wisdom, Mindful Solutions.
    design:
      columns: '2'
  - block: accomplishments
    content:
      # Note: `&shy;` is used to add a 'soft' hyphen in a long heading.
      title: 'Accomplish&shy;ments'
      subtitle:
      # Date format: https://docs.hugoblox.com/customization/#date-format
      date_format: Jan 2006
      # Accomplishments.
      #   Add/remove as many `item` blocks below as you like.
      #   `title`, `organization`, and `date_start` are the required parameters.
      #   Leave other parameters empty if not required.
      #   Begin multi-line descriptions with YAML's `|2-` multi-line prefix.
      items:
        - certificate_url: 
          date_end: '2012-05-01'
          date_start: '2011-05-01'
          description: 'I volunteered in various capacities for a reading fair started by a fellow Stanford Alumni for youth in disadvantaged areas of the San Francisco Bay Area. I solicited donations for raffle prizes, set up and ran fun reading activities, and coordinated other volunteers at check-in.'
          icon: 
          organization: Reading Rainbow in the Park
          organization_url: http://readinginthepark.org/
          title: Planning Committee
          url: ''
        - certificate_url: 
          date_end: ''
          date_start: '2009-08-01'
          description: 'I developed a civic action mapping web presence and organized national synchronous marches to rally thousands of American people to pressure our government into passing a healthcare reform bill with a strong public option.'
          icon: 
          organization: March4Healthcare
          organization_url: https://www.march4healthcare.com
          title: Organizing Grassroots Healthcare Activists
          url: 
    design:
      columns: '2'
  - block: slider
    content:
      slides:
        - title: Debating Executive Control of the Internet
          content: '&#8220;If government authority weren’t acting in good faith for the public welfare, they might find any legal or technical control over the Internet irresistible to abuse, especially if they weren’t knowledgeable of or concerned with the potential ramifications of exercising such power.&#8221;'
          align: center
          background:
            image:
              # Specify an image from `assets/media/`
              # or delete the image section to remove it
              filename: 
              filters:
                brightness: 0.7
            position: center
            color: '#666'
            gradient_end: '#ed4a72'
            gradient_start: '#004ba0'
            text_color_light: true
          link:
            icon: book-open
            icon_pack: fas
            text: Read More
            url: 'post/debating-executive-control-of-the-internet-a-critical-ethical-analysis-of-the-kill-switch-bill/'
        - title: How an Equation Changed Warfare
          content: '&#8220;It only takes one irrational leader to start a world war. It only took one equation to change warfare. As Einstein himself put it, &#8220;Politics are for the moment. An equation is for eternity&#8221;&#8221;'
          align: center
          background:
            image:
              # Specify an image from `assets/media/`
              # or delete the image section to remove it
              filename: 
              filters:
                brightness: 0.7
            position: center
            color: '#666'
            gradient_end: '#004ba0'
            gradient_start: '#ed4a72'
            text_color_light: true
          link:
            icon: book-open
            icon_pack: fas
            text: Read More
            url: 'post/how-an-equation-changed-warfare/'
        - title: The Status of Women in Computer Science
          content: '&#8220;The lack of female computer scientists can be attributed to the negative effects of cultural stereotypes, barriers in the educational system, and the small number of female role models for young women; outreach programs, increased awareness of the problem, and a changing economic climate may increase the percentage of women in computer science.&#8221;'
          align: center
          background:
            image:
              # Specify an image from `assets/media/`
              # or delete the image section to remove it
              filename: 
              filters:
                brightness: 0.7
            position: center
            color: '#666'
            gradient_end: '#ed4a72'
            gradient_start: '#004ba0'
            text_color_light: true
          link:
            icon: book-open
            icon_pack: fas
            text: Read More
            url: 'post/the-status-of-women-in-computer-science/'
        - title: Ethereal Expression - The History and Significance of the Theremin
          content: '&#8220;At the dawn of the age of electricity, a Russian physicist named Lev Terman developed a new instrument that would allow composers and performers to transcend musical limits.&#8221;'
          align: center
          background:
            image:
              # Specify an image from `assets/media/`
              # or delete the image section to remove it
              filename: 
              filters:
                brightness: 0.7
            position: center
            color: '#666'
            gradient_end: '#004ba0'
            gradient_start: '#ed4a72'
            text_color_light: true
          link:
            icon: book-open
            icon_pack: fas
            text: Read More
            url: 'post/ethereal-expression/'
    design:
      # Slide height is automatic unless you force a specific height (e.g. '400px')
      slide_height: ''
      # Make the slides full screen within the browser window?
      is_fullscreen: true
      # Automatically transition through slides?
      loop: false
      # Duration of transition between slides (in ms)
      interval: 2000
  - block: collection
    id: posts
    content:
      title: Recent Posts
      subtitle: ''
      text: ''
      # Choose how many pages you would like to display (0 = all pages)
      count: 5
      # Filter on criteria
      filters:
        folders:
          - post
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
      view: compact
      columns: '2'
# - block: portfolio
#   id: projects
#   content:
#     title: Projects
#     filters:
#       folders:
#         - project
#     # Default filter index (e.g. 0 corresponds to the first `filter_button` instance below).
#     default_button_index: 0
#     # Filter toolbar (optional).
#     # Add or remove as many filters (`filter_button` instances) as you like.
#     # To show all items, set `tag` to "*".
#     # To filter by a specific tag, set `tag` to an existing tag name.
#     # To remove the toolbar, delete the entire `filter_button` block.
#     buttons:
#       - name: All
#         tag: '*'
#       - name: Deep Learning
#         tag: Deep Learning
#       - name: Other
#         tag: Demo
#   design:
#     # Choose how many columns the section has. Valid values: '1' or '2'.
#     columns: '1'
#     view: showcase
#     # For Showcase view, flip alternate rows?
#     flip_alt_rows: false
# - block: markdown
#   content:
#     title: Gallery
#     subtitle: ''
#     text: |-
#       {{< gallery album="demo" >}}
#   design:
#     columns: '1'
  - block: collection
    id: featured
    content:
      title: Featured Publications
      filters:
        folders:
          - post
        featured_only: true
    design:
      columns: '2'
      view: card
# - block: collection
#   content:
#     title: Recent Publications
#     text: |-
#       {{% callout note %}}
#       Quickly discover relevant content by [filtering publications](./publication/).
#       {{% /callout %}}
#     filters:
#       folders:
#         - publication
#       exclude_featured: true
#   design:
#     columns: '2'
#     view: citation
  - block: collection
    id: talks
    content:
      title: Recent & Upcoming Talks
      filters:
        folders:
          - talk
    design:
      columns: '2'
      view: compact
  - block: tag_cloud
    content:
      title: Popular Topics
    design:
      columns: '2'
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
