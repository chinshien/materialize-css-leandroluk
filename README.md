## Custom MaterializeCSS implementation

This project has been improved thinking to complement the same with the ideology used in the jQuery (native to the project) library for the selection of different components. 

The jQuery library internally uses the `document.querySelectorAll()` selector to capture HTML elements on the DOM and such a function allows both classes, tags, or attributes of this element (or elements) to be used.

MaterializeCSS (forked in version v0.98.0) works with the selection only by the 'id' attribute and this restricts the possibilities for the developer besides forcing the declaration of an attribute that is not necessarily mandatory for solutions on the web. 

## The idea behind this project: 

* allow any selector to be used for any component without the need to declare tag's
* optimize the library's code as possible to reduce size.
* reformulate methods to improve their understanding (when necessary)

## Current changes

Below are all the modifications made to library optimization. 

> **Note:** The modifications below do not change the structure of the same

##### SideNav - http://materializecss.com/side-nav.html
* Changed how to select element for jQuery pattern (same css selector structure).
* Optimized code (removing unnecessary block declarations, implementing tenuous comparisons where possible)

##### Dropdown - http://materializecss.com/dropdown.html
* Changed how to select element for jQuery pattern (same css selector structure).
* Optimized code (removing unnecessary block declarations, implementing tenuous comparisons where possible)

##### Modal - http://materializecss.com/modals.html
* Changed location where modal-overflow is created. Now the same is created after the Modal main element. (This is necessary so that there is no problem regarding the positioning of modal-overlow that ends up overlapping the modal).
* Implemented the header for modal (similar to bootstrap) the modal structure was also changed to support not only classes but also the html5 dom logical structure. See the example below:

<!-- language:html5 -->
    <div class="modal">
        <header> <!-- or use ".modal-header" class -->
            <h1> <!-- or use "h2, h3, h4, h5, h6" HTMLElements or ".text" class -->
                Loren Ipsum
            </h1>
            <nav> <!-- or use ".nav-link" class -->
                <a href="#"><i class="material-icons">keyboard_arrow_down</i></a>
                <a href="#"><i class="material-icons">close</i></a>
            </nav>
        </header>
            <main>
              <h1>What is Lorem Ipsum?</h1>
              <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged.</p>
            </main>
        <footer> <!-- or use default class ".modal-footer" -->
            <a class="modal-action modal-close waves-effect waves-green btn-flat">Agree</a>
            <a class="waves-effect waves-green btn-flat">Close</a>
        </footer>
    </div><!-- /.modal -->
