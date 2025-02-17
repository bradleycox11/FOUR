import React, { useState } from 'react';
import { Card, CardContent } from '@/components/ui/card';
import { Button } from '@/components/ui/button';

const classes = [
  { day: 'Tuesday', time: '16:00 AM', name: 'Strength and Conditioning' },
  { day: 'Wednesday', time: '17:30 PM', name: 'Strength and Conditioning' },
  { day: 'Friday', time: '09:00 AM', name: 'Strength and Conditioning' },
  { day: 'Saturday', time: '10:00 AM', name: 'Strength and Conditioning' }
];

const Booking = () => {
  const [booked, setBooked] = useState([]);

  const handleBooking = (className) => {
    if (!booked.includes(className)) {
      setBooked([...booked, className]);
      alert(`You have booked ${className}`);
    } else {
      alert(`You have already booked ${className}`);
    }
  };

  return (
    <div className="min-h-screen bg-gray-100 p-4">
      <div className="w-full max-w-4xl mx-auto mb-8">
        <iframe 
          src="https://book.squareup.com/appointments/a4hrnmy6ncmnxt/location/LF954PK0WT3Y2/availability" 
          className="w-full h-[800px] rounded-2xl shadow-lg border-0"
          title="Square Booking"
          loading="lazy"
        ></iframe>
      </div>
      <h1 className="text-3xl font-bold text-center text-[#137DC5] mb-8">Book Your Class</h1>
      <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        {classes.map((cls, index) => (
          <Card key={index} className="bg-white rounded-2xl shadow-lg p-4">
            <CardContent>
              <h2 className="text-xl font-semibold text-[#004E99]">{cls.name}</h2>
              <p className="text-gray-600">{cls.day} - {cls.time}</p>
              <Button 
                onClick={() => handleBooking(cls.name)} 
                className="mt-4 bg-[#137DC5] text-white hover:bg-[#004E99]">
                Book Now
              </Button>
            </CardContent>
          </Card>
        ))}
      </div>
    </div>
  );
};

export default Booking;# FOUR
PT
