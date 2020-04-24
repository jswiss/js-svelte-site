<style>
  ul {
    margin: 0;
    padding: 0;
  }

  /* clearfix */
  ul::after {
    content: "";
    display: block;
    clear: both;
  }

  li {
    display: block;
    float: right;
  }

  a {
    text-decoration: none;
    padding: 1em 0.5em;
    display: block;
  }

  .twitter {
    width: 32px;
    height: 32px;
    background-color: #f5f5f5;
    -webkit-mask: url(twitter-icon.svg) no-repeat center;
    mask: url(twitter-icon.svg) no-repeat center;
  }
  .github {
    width: 32px;
    height: 32px;
    background-color: #f5f5f5;
    -webkit-mask: url(github-icon.svg) no-repeat center;
    mask: url(github-icon.svg) no-repeat center;
  }
  .linkedin {
    width: 32px;
    height: 32px;
    background-color: #f5f5f5;
    -webkit-mask: url(linkedin-icon.svg) no-repeat center;
    mask: url(linkedin-icon.svg) no-repeat center;
  }
  .email {
    width: 32px;
    height: 32px;
    background-color: #f5f5f5;
    -webkit-mask: url(email-icon.svg) no-repeat center;
    mask: url(email-icon.svg) no-repeat center;
  }
</style>

<footer>
  <div id="footer-left" />
  <ul>
    <li>
      <a href="mailto:josh@joshuaswiss.dev">
        <div class="email" alt="send me an email!" title="send me an email!" />
      </a>
    </li>
    <li>
      <a
        href="https://www.linkedin.com/in/joshuaswiss/"
        target="_blank"
        rel="noopener noreferrer">
        <div
          class="linkedin"
          alt="explore my professional experience!"
          title="explore my professional experience!" />
      </a>
    </li>
    <li>
      <a
        href="https://twitter.com/jswiiiss"
        target="_blank"
        rel="noopener noreferrer">
        <div
          class="twitter"
          alt="see what I tweet!"
          title="see what I tweet!" />
      </a>
    </li>
    <li>
      <a
        href="https://github.com/jswiss"
        target="_blank"
        rel="noopener noreferrer">
        <div
          class="github"
          alt="check out my repos!"
          title="check out my repos!" />
      </a>
    </li>
  </ul>
</footer>
