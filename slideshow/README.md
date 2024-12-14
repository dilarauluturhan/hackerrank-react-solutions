<div align="center">
  <h1 align="center">HackerRank - React - Slideshow Solution</h1>
</div>

```
import React, { useState } from "react";

function Slides({ slides }) {
  const [currentSlideIndex, setCurrentSlideIndex] = useState(0);

  const isFirstSlide = currentSlideIndex === 0;
  const isLastSlide = currentSlideIndex === slides.length - 1;

  const handleNext = () => {
    if (!isLastSlide) {
      setCurrentSlideIndex(currentSlideIndex + 1);
    }
  };

  const handlePrev = () => {
    if (!isFirstSlide) {
      setCurrentSlideIndex(currentSlideIndex - 1);
    }
  };

  const handleRestart = () => {
    setCurrentSlideIndex(0);
  };

  return (
    <div>
      <div id="navigation" className="text-center">
        <button data-testid="button-restart" onClick={handleRestart}
          disabled={isFirstSlide} className="small outlined">
          Restart
        </button>
        <button data-testid="button-prev" onClick={handlePrev}
          disabled={isFirstSlide} className="small">
          Prev
        </button>
        <button data-testid="button-next" onClick={handleNext}
          disabled={isLastSlide} className="small">
          Next
        </button>
      </div>
      <div id="slide" className="card text-center">
        <h1 data-testid="title">{slides[currentSlideIndex].title}</h1>
        <p data-testid="text">{slides[currentSlideIndex].text}</p>
      </div>
    </div>
  );
}

export default Slides;
```
