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
Yes, when creating the proxima_centauri it added the distance_ly 4.246.
then the @distance_km used that to get the distance in KM.  The print_distance
has a puts function that puts in the @distance_km within its string, with The
output of @distance_km= 40170261586578.086
```

## Ruby Object Variables: Part II

Does `proxima_centauri.print_mass` run? Why or why not? If so, then what is the
output? If not, then how can it be fixed?

```md
No, it does not have the @ for mass_kg so it wont run.  to fix the issue you will
to add the @mass_kg for the key and the print_mass will need #{@mass_kg}
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
No, the sol is a different object then the_sun.  They may be under the same class
but they will not affect each other if change or removed unless there is a method
that uses both of them.
```

## Ruby Object Equality: Part II

Will modifying `the_sun` affect `nearest_star`? Why or why not?

```md
Yes it will.  The nearest_star calls on 'the_sun' and if the value etc changes, it
will affect the nearest_star.
```

## JavaScript Objects

Create an object literal named `vega` with the following properties and values.

| Property | Value |
| --- | --- |
| distance | 25.04 |
| solarMass | 2.135 |

```javascript
const vega = {
  distance: 25.04,
  solarMass: 2.135
}
```

## Ruby vs. JavaScript

If, in the above code, `var`, `let`, or `const` were removed and the code were
executed as Ruby code, what type of object will be created?

```md
vega would be a hash with the following keys of distance: 25.04, solarMass: 2.135
```
