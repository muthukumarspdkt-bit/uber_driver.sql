# uber_driver.sql
Mysql project 

CREATE TABLE drivers (
    driver_id INT PRIMARY KEY IDENTITY(1,1),
    driver_name VARCHAR(100) NOT NULL,
    vehicle_type VARCHAR(10) NOT NULL,
    vehicle_name VARCHAR(50) NOT NULL,
    city VARCHAR(50) NOT NULL,
    status VARCHAR(15) NOT NULL,
    issue VARCHAR(MAX),
    created_at DATETIME2 DEFAULT GETDATE(),
    updated_at DATETIME2 DEFAULT GETDATE()
);
GO

-- Insert 55+ Driver Records with diverse vehicle types
INSERT INTO drivers (driver_name, vehicle_type, vehicle_name, city, status, issue) VALUES
-- Bike drivers
('Rajesh Kumar', 'bike', 'Honda Activa', 'Bangalore', 'active', 'None'),
('Priya Sharma', 'bike', 'TVS Jupiter', 'Mumbai', 'active', 'Low earning concern'),
('Amit Patel', 'bike', 'Suzuki Access', 'Delhi', 'waitlisted', 'Asking extra money from customers'),
('Sunita Reddy', 'bike', 'Hero Maestro', 'Hyderabad', 'rejected', 'Duplicate ID found'),
('Vijay Singh', 'bike', 'Yamaha Fascino', 'Pune', 'applied', 'Under verification'),
('Mohammed Ali', 'bike', 'Honda Dio', 'Bangalore', 'active', 'Vehicle maintenance issue'),
('Kavita Nair', 'bike', 'TVS Ntorq', 'Kochi', 'active', 'Health issue - diabetes management'),
('Sneha Desai', 'bike', 'Suzuki Burgman', 'Ahmedabad', 'active', 'Personal issue - family emergency'),
('Anjali Verma', 'bike', 'Honda Activa 6G', 'Jaipur', 'applied', 'Documents under review'),
('Pooja Singh', 'bike', 'TVS Jupiter ZX', 'Delhi', 'active', 'None'),
('Pallavi Jain', 'bike', 'Hero Pleasure', 'Jaipur', 'active', 'Seasonal issue - tourist season'),
('Seema Roy', 'bike', 'Yamaha Ray ZR', 'Guwahati', 'reactivation', 'Document issue - bank details update'),

-- Auto drivers
('Lakshmi Iyer', 'auto', 'Bajaj RE Auto', 'Chennai', 'reactivation', 'Document issue - expired license'),
('Deepak Mehta', 'auto', 'Piaggio Ape', 'Mumbai', 'waitlisted', 'Operating multiple vehicles with different IDs'),
('Rahul Gupta', 'auto', 'Mahindra Alfa', 'Delhi', 'rejected', 'Duplicate ID - account suspended'),
('Karthik Rao', 'auto', 'TVS King', 'Bangalore', 'active', 'Seasonal issue - monsoon affecting rides'),
('Suresh Babu', 'auto', 'Bajaj Maxima', 'Chennai', 'reactivation', 'Document issue - insurance expired'),
('Arun Kumar', 'auto', 'Piaggio Ape City', 'Bangalore', 'waitlisted', 'Customer complaints - overcharging'),
('Ramesh Pillai', 'auto', 'Mahindra Treo', 'Kochi', 'rejected', 'Duplicate ID verification failed'),
('Sandeep Joshi', 'auto', 'Bajaj RE Compact', 'Pune', 'reactivation', 'Document issue - RC renewal pending'),
('Vikram Malhotra', 'auto', 'TVS King Deluxe', 'Chandigarh', 'applied', 'Background verification in progress'),
('Rekha Patel', 'auto', 'Piaggio Ape Auto', 'Ahmedabad', 'waitlisted', 'Multiple vehicle operation suspected'),
('Govind Sharma', 'auto', 'Mahindra Alfa Plus', 'Indore', 'active', 'Seasonal issue - wedding season high demand'),
('Manoj Tiwari', 'auto', 'Bajaj RE 4S', 'Varanasi', 'rejected', 'Duplicate ID - multiple accounts'),
('Harish Bhat', 'auto', 'TVS King Duramax', 'Mangalore', 'reactivation', 'Document issue - PAN card update needed'),
('Swati Kulkarni', 'auto', 'Piaggio Ape Xtra', 'Pune', 'waitlisted', 'Asking extra fare from passengers'),
('Nandini Rao', 'auto', 'Mahindra Treo Zor', 'Mysore', 'applied', 'Documents submitted'),
('Geeta Menon', 'auto', 'Bajaj RE Electric', 'Trivandrum', 'reactivation', 'Document issue - address proof pending'),
('Sanjay Mishra', 'auto', 'TVS King Electric', 'Bhopal', 'rejected', 'Duplicate ID found in system'),
('Naresh Yadav', 'auto', 'Piaggio Ape E-City', 'Delhi', 'waitlisted', 'Driving multiple vehicles with different IDs'),
('Usha Rani', 'auto', 'Mahindra Alfa Load', 'Ranchi', 'rejected', 'Duplicate ID verification failed'),
('Bharti Agarwal', 'auto', 'Bajaj Qute', 'Surat', 'waitlisted', 'Customer complaints about extra charges'),

-- Car drivers
('Neha Kapoor', 'car', 'Hyundai Creta', 'Mumbai', 'active', 'Low earning - night shift preference'),
('Divya Krishnan', 'car', 'Hyundai Venue', 'Hyderabad', 'active', 'Vehicle issue - AC malfunction'),
('Meera Devi', 'car', 'Toyota Etios', 'Lucknow', 'active', 'Health issue - back pain'),
('Shalini Reddy', 'car', 'Honda City', 'Hyderabad', 'active', 'Low earning complaint'),
('Anita Deshmukh', 'car', 'Toyota Innova', 'Nagpur', 'active', 'Personal issue - child care'),
('Pradeep Nair', 'car', 'Maruti Ertiga', 'Kochi', 'active', 'Vehicle issue - tire replacement needed'),
('Ravi Chandra', 'car', 'Hyundai Venue', 'Visakhapatnam', 'active', 'None'),
('Ashok Kumar', 'car', 'Toyota Etios', 'Coimbatore', 'active', 'Health issue - routine checkup'),
('Kavita Bose', 'car', 'Maruti Ertiga', 'Kolkata', 'active', 'Low earning due to area preference'),
('Prakash Shetty', 'car', 'Toyota Innova', 'Bangalore', 'active', 'Vehicle issue - engine servicing'),
('Madhuri Sinha', 'car', 'Hyundai Creta', 'Patna', 'applied', 'Application under review'),
('Dinesh Pillai', 'car', 'Honda City', 'Chennai', 'reactivation', 'Document issue - fitness certificate expired'),
('Radha Krishna', 'car', 'Maruti Dzire', 'Hyderabad', 'active', 'Personal issue - relocation planning'),
('Ajay Thakur', 'car', 'Hyundai Venue', 'Shimla', 'active', 'Seasonal issue - winter tourism'),
('Mohan Das', 'car', 'Toyota Etios', 'Bhubaneswar', 'active', 'None'),
('Kishore Kumar', 'car', 'Maruti Ertiga', 'Vijayawada', 'active', 'Health issue - eye checkup scheduled'),
('Brijesh Pandey', 'car', 'Honda Amaze', 'Kanpur', 'active', 'Low earning - switching to peak hours'),
('Archana Iyer', 'car', 'Maruti Dzire', 'Kochi', 'applied', 'Waiting for onboarding'),
('Nitesh Agarwal', 'car', 'Toyota Innova', 'Mumbai', 'active', 'Vehicle issue - brake system check'),
('Shilpa Hegde', 'car', 'Hyundai Creta', 'Bangalore', 'waitlisted', 'Multiple account operation suspected'),
('Ranjit Singh', 'car', 'Honda City', 'Amritsar', 'active', 'Seasonal issue - festival rush'),
('Vaishali Chopra', 'car', 'Maruti Swift', 'Delhi', 'rejected', 'Duplicate ID - policy violation'),
('Ganesh Murthy', 'car', 'Hyundai Venue', 'Chennai', 'active', 'Personal issue - health insurance claim'),
('Sunil Kapoor', 'car', 'Maruti Swift', 'Bangalore', 'active', 'None'),
('Preeti Agarwal', 'car', 'Honda Jazz', 'Mumbai', 'active', 'Low earning - peak hour strategy'),
('Anil Verma', 'car', 'Hyundai i20', 'Delhi', 'active', 'Vehicle issue - suspension check needed');
GO

--SELECT, COUNT(*) as driver_count
--FROM drivers
--GROUP BY status
--ORDER BY driver_count DESC;

SELECT
    driver_name,
    city,
    vehicle_name,
    issue,
    status
FROM drivers
WHERE status = 'active';

SELECT vehicle_type, COUNT(*) as active_count
FROM drivers
WHERE status = 'active'
GROUP BY vehicle_type;


SELECT status AS dp_status, COUNT(*) AS driver_count
FROM drivers
GROUP BY status;

SELECT*
FROM drivers
where  city in ('Chennai') ;

SELECT DVP.city, DVP.vehicle_name
FROM drivers AS DVP
WHERE DVP.vehicle_name LIKE '%Bajaj%';
