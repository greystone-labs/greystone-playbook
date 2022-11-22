# Best Practices for React Applications

The development community is vast and we take the approach that no individual is wiser than the group, so we leverage community best practices where possible. 

Use community curated guidelines and best practices as the default standard and document any changes on a case by case basis.

## Testing:
* https://github.com/abinoda/rspec-best-practices
* https://github.com/rubocop/rspec-style-guide
* https://rspec.rubystyle.guide/
* https://github.com/rubocop/ruby-style-guide
* [more rspec](https://relishapp.com/rspec/)
* [AAA](https://blog.devgenius.io/the-three-as-of-unit-testing-3b8b4bf0d087)

## OOP

### Code smells and OOP principles
* https://github.com/troessner/reek/tree/master/docs

### Hexigonal Architecture
Resources:
* [Clean Code](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html)
* [Corey Haines' talk](https://www.youtube.com/watch?v=bNn6M2vqxHE)
* [Bob Martin's talk](https://www.youtube.com/watch?v=WpkDN78P884)
* [Jim Weirich's talk](https://www.youtube.com/watch?v=tg5RFeSfBM4)
* [Jim Weirich's code](https://gist.github.com/dhh/4849a20d2ba89b34b201)
* [DHH's "test induced design damage"](http://david.heinemeierhansson.com/2014/test-induced-design-damage.html)
* [Bob Martin's reply to DHH](http://blog.8thlight.com/uncle-bob/2014/05/01/Design-Damage.html)
* [DHH's gist against Jim's approach](https://gist.github.com/dhh/4849a20d2ba89b34b201)
* [Partial Alternative to Jim's Approach](http://www.patmaddox.com/2014/05/15/poof-and-then-rails-was-gone/)
* [Article on Hexigonal Architecture](http://alistair.cockburn.us/Hexagonal+architecture)

## Ruby:
* [Ruby Style Guide](https://github.com/rubocop/ruby-style-guide)
* [Rails Cops](https://docs.rubocop.org/rubocop-rails/cops.html)

## React:
Best Practices for Modern React Apps as of (Sept 2022)

- Extract rendered jsx components into own rendered function, do not nest rendered functions

Before
```
const Parent = () => {
  const SecondChild = () => {
    return <div> ... </div>
  }
    
  const Child = () => {
    return <div> ... </div>
  }

  return (
    <div>
     <Child/>
     <SecondChild />
    </div>
  )
}
```

After
```
  const Child = () => {
    return <div>... </div>
  }

  const SecondChild = () => {
    return <div> ... </div>
  }

const Parent = () => {

  return (
    <div>
     <Child/>
     <SecondChild />
    </div>
  )
}
```

- Consider using "React Context" when child prop drilling dependency exceeds grandchild 

- Use "UseMemo" when logic heavy or expensive functions do not have a jsx render (i.e. Data Transformation, caculations) 

- Decouple nested state objects wherever possible to aviod multiple re-renders, creating "custom hooks" to return only the needed values can avoid unnecessary renders 

- Avoid hard coded values to determine logical pathing. Using an object as dictionary is a better approach.

- Function based file naming conventions. Name files by the primary function and the subject it acts upon. i.e. "createTasks" vs "create" 

## DevOps:
* Terraform
* Containerization
* Centralized logging
