# The Marker Match Database

## Overview

The MarkerMatch Database is the current list of all markers and colored pencils listed in the MarkerMatch app along with their color values in hex, RGB and CMYK. The file is in CSV format.

You are free to use these values.

### DeltaE Calculation

Calculating the difference between two colors is trivial once you have converted both to Lab

```csharp
/// <summary>Takes two colors as Lab color arrays. Square the difference of each channel and then sum.</summary>
/// <param name="lab1">Lab color array as double array</param>
/// <param name="lab2">Lab color array as double array</param>
/// <returns>A DeltaE comparison value where 0 means identical and increasing value is a greater difference.</returns>
public static double CalcDeltaE( double[] lab1, double[] lab2)
{
	// validate the input first

	return Math.Sqrt( Math.Pow(lab2[0] - lab1[0], 2) + Math.Pow( lab2[1] - lab1[1], 2) + Math.Pow( lab2[2] - lab1[2], 2));
}
```

## API

There is a REST API for matching against the database.
