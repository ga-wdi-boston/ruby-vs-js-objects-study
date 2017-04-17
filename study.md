# Ruby vs. JavaScript: Objects Study

Use your favorite search engine and the provided readings to research and
respond to the following questions.

In your responses, be sure to cite any relevant sources you consulted in your
search. We ask you to write responses in your own words in order to see how you
process what you've read. Please do not respond with direct quotes from source
material. Instead, digest what you've read and repeat it in your own voice.

## Required Readings

-   [Ruby-Doc.org: Variables](http://ruby-doc.org/docs/ruby-doc-bundle/UsersGuide/rg/variables.html)
-   [Ruby-Doc.org: Instance Variables](http://ruby-doc.org/docs/ruby-doc-bundle/UsersGuide/rg/instancevars.html)
-   [Ruby-Doc.org: Local Variables](http://ruby-doc.org/docs/ruby-doc-bundle/UsersGuide/rg/localvars.html)

## Ruby Object Variables: Part I

Assume that we have the following class and an instance of it to work with.

```ruby
class Star
  def initialize(distance_ly, mass_solar)
    @distance_km = distance_ly * 9_460_730_472_580.8
    mass_kg = mass_solar * (1.99 * 10 ** 30)
  end

  def print_distance
    puts "The star is approximately #{@distance_km} kilometers away."
  end

  def print_mass
    puts "The star has a mass of approximately #{mass_kg} kilograms."
  end
end

proxima_centauri = Star.new(4.246, 0.123)
```

Does `proxima_centauri.print_distance` run? Why or why not? If so, then what is
the output? If not, then how can it be fixed?

```md
It does run and the output is:
The star is approximately 40170261586578.086 kilometers away.
print_distance is a method of the class Star so the .new method that creates the object star proxima_centauri can access the methods defined in the class Star.
```

## Ruby Object Variables: Part II

Does `proxima_centauri.print_mass` run? Why or why not? If so, then what is the
output? If not, then how can it be fixed?

```md
No. the error message is: NameError: undefined local variable or method `mass_kg'.

the print_mass method does not work because mass_kg is not declared as an instance variable with @ and therefore cannot be accessed outside of the initialize method.
```

## Ruby Object Equality: Part I

Suppose that we have the following block of code.

```ruby
sol = Star.new(0, 1)
the_sun = Star.new(0, 1)
nearest_star = the_sun
```

Will modifying `sol` affect `the_sun`? Why or why not?

```md
no, they are different objects
```

## Ruby Object Equality: Part II

Will modifying `the_sun` affect `nearest_star`? Why or why not?

```md
no, instansiating the_sun as a new star and then instansiating nearest_star to the_sun will give both objects the same id. when you rerun the .new method on the sun to change it, it generates a new ID and the data associated with the_sun is different than what is associated with nearest_star.
```

## JavaScript Objects

Create an object literal named `vega` with the following properties and values.

| Property | Value |
| --- | --- |
| distance | 25.04 |
| solarMass | 2.135 |

```javascript
const objLiteral = {
  distance: 25.04,
  solarMass: 2.135
}
```

## Ruby vs. JavaScript

If, in the above code, `var`, `let`, or `const` were removed and the code were
executed as Ruby code, what type of object will be created?

```md
it does work, and it creates hashes:
{:distance=>25.04, :solarMass=>2.135}
```
