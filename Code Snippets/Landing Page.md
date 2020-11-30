Add description here.

```
const Title = () => <h1 className="Title">SocialChains</h1>;

class Row extends React.Component {
  
  render() {
    return <div className="Row">{ this.props.children }</div>;
  };
  
};

// The main navigation component -- this allows the user to move to the next page in the onboarding flow.
const Nav = () => (
  <nav className="Nav">
    <ul>
      <Row>
        <li><Link text="Get Started" /></li>
      </Row>
    </ul>
  </nav>
);

// Adding a link to the button.
class Link extends React.Component {
  
  render() {
    let className = `Link Link--${this.props.type}`;
    return <a href="#" className={ className }>{ this.props.text }</a>
  };
  
};

Link.defaultProps = {
  type: "primary"
};

// The landing page.
const LandingPage = () => (
  <header className="LandingPage">
    <Title />
    <Row>
      <Dot />
      <Dot type="accent" />
      <Dot />
    </Row>
    <Nav />
  </header>
);

// Render the landing page.
ReactDOM.render(<LandingPage />, document.body);

```
