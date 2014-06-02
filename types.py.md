Imports.  Woot!

    from random import (
      randint,
     )
    from sys import maxsize 

A class for constructing a range of numbers from [j,k]
and generating new values within that range.

    class NumberRange(object):
      
      def __init__(self, minimum, maximum, distribution_function):
        self.minimum = minimum
        self.maximum = maximum
        self.distribution_function = distribution_function

      def value(self):
        return self.distribution_function(self.minimum, self.maximum)

A class for constructing a range of integers from [j,k]
and generating new values within that range.

    class IntegerRange(object):
      
      def __init__(self, minimum=-maxsize, maximum=maxsize, distribution_function=randint):
        self.minimum = minimum
        self.maximum = maximum

      def value(self):
        return randint(self.minimum, self.maximum)

A class for constructing a range of integers from [j,0)
and generating new values within that range.

    class NegativeIntegerRange(IntegerRange):
      
      def __init__(self, minimum=-maxsize):
        self.minimum = minimum
        self.maximum = -1

A class for constructing a range of integers from [j,0]
and generating new values within that range.

    class NonPositiveIntegerRange(IntegerRange):
      
      def __init__(self, minimum=-maxsize):
        self.minimum = minimum
        self.maximum = 0

A class for constructing a range of integers from [0,k]
and generating new values within that range.

    class NonNegativeIntegerRange(IntegerRange):
      
      def __init__(self, maximum=maxsize):
        self.minimum = 0
        self.maximum = maximum

A class for constructing a range of integers from (0,k]
and generating new values within that range.

    class PositiveIntegerRange(IntegerRange):
      
      def __init__(self, maximum=maxsize):
        self.minimum = 1
        self.maximum = maximum
