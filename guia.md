# Guia de react

React es una librera que esta ligada a javascript y nodejs, es una documentación para interfazes de paginas web

## metodos
recibe datos de entrada y retórna que demostrar
~~~bash
render()
~~~

metodo para aceder a los datos de entrada que pasan por el metodo render
~~~bash
this.props
~~~

acceder a los datos de estado interno
~~~bash
this.state
~~~

## Ejemplos
muestra el nombre

Metodos usados:

-render

-this.props
~~~bash
class helloMessage extends React.Component {
render(){
        return <div>Hola {this.props.name}</div>;
    }
}
root.render(<HelloMessage name="Taylor" />);
~~~


Contador incremental

Metodos:

~~~bash
class timer extends React.Component {
    constructor(props){
        super(props);
        this.state = {seconds: 0};
}

tick(){
    this.setState(state => ({seconds: state.seconds +1}));
}

componentDidMount(){
    this.interval =setinterval(()=> this.tick(), 1000);
}

componentWillUnmoint() {
    clearInterval(this.interval);
}

render(){
    return (
        <div>
            segunos: {this.state.seconds}
        </div>
);
}
}

root.render(<Timer />);
~~~


Aplicación usando props y state que genera una lista que se actualiza y se enumera conforme metes los datos en el recuadro y confirmas.

~~~bash
class TodoApp extends React.Component{
contructor(props) {
    super(props);
    this.state={items: [], text: ''};
    this.handleChange=this.hanldeChange.bind(this);
    this.hondleSubmit=this.HandleSubmt.bind(this);
}

render(){
    return(
    <div> 
    <h3>Tareas pendientes</h3>
    <TodoList items={this.state.items} />
    
    </div>
)
}
}
~~~