Add descriptive text here.

```
const Sidebar = ({children}) => {
  var sidebarStyle = {
    position: 'absolute',
    width: '230px',
    height: '100%',
    background: '#2A3F54',
    zIndex: 9999,
    display: 'flex'
  };
  
  return (
    <div className="sidebar col-md-3" style={sidebarStyle}>
      {children}  
    </div>
  )
}

const PageView = ({page}) => {
  var viewStyles = {
    marginLeft: '230px',
    padding: '10px 20px 0'
  }
  return (
    <Title text="SocialChains Opportunities Dashboard" />
  )
}

const MenuItem = ({title, icon}) => {
  var menuItemStyle = {
    display: 'block',
    padding: '10px',
    color: '#fdfdfd',
    margin: '0 -15px',
    borderBottom: '1px solid rgb(35, 50, 66)'
  };
  
  var iconStyle = {
    marginRight: '10px'
  }
  
  return (
    <a href="#" style={menuItemStyle}>
      <i className={'fa fa-fw fa-' + icon} style={iconStyle}></i>
      {title}
    </a>  
  )
}

const Menu = ({pages}) => {
  var navStyle = {
    display: 'block',
    width: '100%'
  };
  return (
    <nav style={navStyle} >
      {pages.map((page) => {
        return <MenuItem title={page.name} icon={page.icon} />
      })}
    </nav>
  )
}

const Title = ({text}) => {
  return (
    <div className="text-center page-header">
      {text}
    </div>
  )
};

class Dashboard extends React.Component {
  constructor(props) {
    super(props);
    
    this.state = {
      pages: [
        {
          "id": "1",
          "name": "Company A",
          "children": []
        },
        {
          "id": "2",
          "name": "Company B",
          "children": []
        },
        {
          "id": "3",
          "name": "Company C",
          "children": []
        },
        {
          "id": "4",
          "name": "Company D",
          "children": []
        },
        {
          "id": "5",
          "name": "Company E",
          "children": []
        }
      ]
    };
  }
  
  render() {
    return (
      <div className="container-fluid">
        <div className="row">
          <Sidebar>
            <Menu pages={this.state.pages} />
          </Sidebar>
          <PageView page={this.state.pages[0]} />
        </div>
      </div>
    );
  }
}

ReactDOM.render(<Dashboard />, document.getElementById('root'));
```
